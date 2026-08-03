+++
title = "Automatically updated indexes"
author = ["Brian McCrory"]
publishDate = 2026-04-23
lastmod = 2026-04-23
tags = [""]
categories = ["blog"]
draft = false
slug = "v5-1-automatically-updated-indexes"
hiddenInHomeList = true
+++

Most of my articles on _Jazz of Japan_ were about individual albums. During the periods that I was publishing on Substack (in [v2.0](/blog/v2-0-substack/) and [v4.0](/blog/v4-0-substack/)), the articles appeared in my Substack archive as a flat list ordered by date with a thumbnail image and an excerpt. To supplement this archive-style index, I wanted to present the articles as a list of albums ordered by album release year, not just by the article post date (Albums Index). In addition, I wanted to create an index of all musicians included on all albums, with links to each album (each article) that each musician appears on (Musicians Index). Finally, I also wanted a timeline-based list of articles to show the oldest to newest issues, like the Substack archive but simpler and customized for my article types (Articles Index, aka Publish History Timeline).

Most importantly, I wanted the indexes to be automatically regenerated each time I published a new article. That is, the new album should be added to the Albums Index, the musicians included on that album should be added to the Musicians Index, and the new article should be added to the Publish History Timeline. I also wanted to be able to easily update the indexes on demand, whenever I fixed a typo or changed a detail for an album, musician, or article.

The overall goals were:

-   When publishing a new article to Substack, automatically update the index pages so I did not have to hand-update those pages on Substack.
-   Use minimal formatting for the index pages so that they are easy to read and search.

Eventually, I thought it would be better to remove the index pages from Substack and host them somewhere else. The reasons for this were:

-   Substack updates to these types of pages were a manual, error-prone process.
-   Substack didn’t display indexes well, as their layout was optimized for paragraphs of prose, not for long lists of links, and had no support for tables or other formatting options.
-   Indexes did not fit within the three general types I was using (albums, clubs, guides).
-   Adding these links to the Substack navigation menu opened them in a new browser tab, treating them as a separate site.
-   Having long index pages with many links could trigger checks or even banning by resembling SEO link farms.
-   Similar issues arose with other index-type pages I wanted to handle, including Audio Mixes and Categories.
-   If and when I stopped publishing on Substack, I wanted to be able to move the indexes as-is along with all articles


## Partially automated updates

My first solution for generating index pages was based using a program to create indexes by parsing the HTML of all the articles I had posted on Substack. This was a program I could run as often as I wanted, within reasonable limits, in order to update the indexes based on all currently published articles. After writing a new article, I would run the program to fetch all published articles, parse them, and collect certain data from each page. Since I was using a standard format in each article to display album information, I could identify and parse my text (for album titles, musicians, etc.) in order to create the indexes and display them however I wanted — as different types of lists, tables, or whatever looked best. This worked but was not a long-term solution, since the program involved parsing HTML from a format that was more-or-less free-form (WYSIWYG in the Substack editor) and not tied to a specific template or markup language.

Plus, I still had to manually update the index pages using the output from the program. Whenever I published a new article on Substack, I also had to update the indexes that I had created as standalone pages on Substack.

Since I wanted to keep my indexes up to date each time I published a new article, I needed to update each index page on Substack with references to each new article. Instead of editing each index and adding the new lines in the right places (which is cumbersome in a browser-based editor for large, dense lists), I decided that it was better to copy-and-paste the entire text of each index with the newly generated text that my program created. This helped reduce the hand-editing involved and the risk of errors.

I was still using a Java program that I wrote early on for this and other tasks, and running this program and copying the output was still one part of my manual publishing pipeline. It was habitual and easy to do, but I wanted to automate more of the process, ideally not having to update several index pages on Substack each time I published something new.

Initially, to parse the HTML, the program would fetch and scrape all articles from my Substack publication through URLs. Later, I changed this to using parsing Substack’s export files, but it was still a brittle process that relied on parsing Substack’s generated HTML.


## Fully automated updates

I eventually moved the index pages from Substack to a static site ([v3.0](/blog/v3-0-github)), and then moving back to publishing on Substack ([v4.0](/blog/v4-0-substack)). This allowed me to automate the process of regenerating index pages and republishing those updates, so that I no longer had to manually update the index pages though cut-and-paste to index pages on Substack.

So, instead of using a Java program to generate index files, I used Jekyll customized templates and layout code (I later changed this custom code [from Jekyll to Hugo](/blog/v4-1-from-jekyll-to-hugo) and Python).

At the same time, I improved the data collection for generating the indexes by parsing my source Markdown files (later, [Org mode files](/blog/v4-2-from-markdown-to-org-mode)) instead of scraped or exported HTML files.


### Script-based updates

The indexes are updated every time a new article is published, not by hand but through the use of a script. This allows new albums and musicians to be added to the Albums Index, Musicians Index, and Timeline pages automatically with no manual editing. These indexes are generated using properties from each article supplemented with data that is normalized and canonical, such as proper and consistent musician names, album titles, musician websites, album labels, years, performing musicians, and other data, along with links to corresponding articles.

In other words, each index is completely recreated each time through an automated script that parses all current articles saved as text files (Org mode markup), plus a few data files. Since the generated indexes themselves are also version controlled using Git, the exact changes can be verified before publishing. As a last step, the regenerated indexes are committed and pushed to GitHub, and the indexes website is automatically republished and refreshed.

At a high-level, all I need to do is write and save articles with some minimal property data (ids, text), run a script to update the indexes, and push the updates to GitHub.


### Org mode files

All my articles are written independent of any particular newsletter platform and are saved as Org mode text files.

With my defined file format, I can include a few properties whose values are special strings for each article:

-   `:id:` unique id for an article as `artist-name-album-title` (aka slug)
-   `:published:` date the article was published as `yyyy-mm-dd`
-   `:members:` list of musician `ids` for this article, with optional overrides
-   etc...

Using structured markup files with defined properties makes the parsing of data more straightforward and complete, compared to what I was doing before by scraping HTML.


### Regenerating and updating indexes

Previously, when an article was ready to be published, I would export it from Org mode to HTML format and copy-and-paste the content into the Substack editor by hand, since Substack has no API. Then I had to follow this with images and media files uploads and positioning. After I moved [from Substack to Buttondown](/blog/v5-0-buttondown), I could use an API to publish articles, and copy-and-paste of article text to a browser editor (with manual uploading of images) was no longer part of the process.

Using the values from all the published articles, and the list of members (referenced through ids), indexes can be generated automatically through the script using article and data files.

The data files (`*.csv`) are used to store additional data in a convenient format and include albums data (release year, label, ...) and musicians data (Japanese name, instrument, website, ...). Each data item is identified by a unique key based on name or title, similar to an URL slug.

The process is:

1.  When a new article is ready to be published, I regenerate the indexes by calling a command line script.
2.  I commit and push the generated indexes to GitHub.
3.  An automatic trigger on GitHub builds and republishes the indexes website.

Separately, because the index files are compatible with Jekyll and Hugo, I can also manage and update the indexes site locally for testing, previewing or changing anything on the site.


### Destination

These indexes are served by a GitHub repo using a custom subdomain assigned through DNS updates and GitHub settings. The root domain `<domain>.com` is the same custom domain used to serve the newsletter and archive (`www.<domain>.com`), but with a different subdomain name (`docs`, `about`, etc.) so that the indexes don’t conflict with the newsletter domain.


## Consolidating resources

Now that I could update articles through Buttondown’s API, I wanted to do the same with the indexes. This also allowed me to move indexes from the subdomain `about.<domain>.com` to the primary domain `www.<domain>.com`. I used the same tools and processes to regenerate and update the resources pages automatically each time a new article was published.

My process still included updating the indexes through an API whenever I published or updated an article, and now I could update the indexes the same way. This replaced the GitHub-based process outlined above, since I had replaced the indexes on that `about` static site with two new `www` articles on Buttondown.

For this change two new articles were added to the archive: [About Jazz of Japan](/about/) and  [Indexes](/indexes/). I set their published date to the original date of the site in 2018, so that they would appear first in the archive. To support links to the `about` site that were previously shared, I added redirects in the old pages to automatically redirect to the new pages.

After this change, everything was on the primary `www` domain, making the indexes appear similar in style and layout to existing articles. This reinforces the fact that the two supplemental pages are on same site as the newsletter and articles (this impression can be weaker or confusing when the pages are located on a separate `about` subdomain with a different look and feel).

Another benefit was that I could remove an extraneous component that was not longer necessary: the `about` static site on GitHub. The fewer moving parts, the better, at least for this type of writing-based project.
