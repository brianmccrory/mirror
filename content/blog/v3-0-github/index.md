+++
title = "Jazz of Japan on GitHub"
author = ["Brian McCrory"]
publishDate = 2022-01-18
lastmod = 2022-01-18
tags = [""]
categories = ["blog"]
draft = false
slug = "v3-0-github"
hiddenInHomeList = true
+++

## January 2022: Moving from Substack to GitHub

Using Substack was great for writing and sending out free-form writing, but there was some extra functionality that I was looking for. Now that I had about 150 articles with many drafts in progress, I wanted to better organize things and have a standard structure that was easier to work with.

Since most of my posts were about albums, I was using a regular layout for each article, like a template with a specific format and well-defined sections.

Specifically, I wanted to my text, musician data, images, links, and audio files stored in a database or some sort of flexible data format. I wanted to have finer-grained control of the data and presentation, like what website content management systems can offer.

For each article, I wanted a data- and template-based system based on:

-   A main body section for the description of the album
-   Images of the album, usually inserted throughout the body text
-   Musician names, instruments, names in Japanese, and website links, all in a standard form that I could easily update later if any data changed
-   Video and audio links that I could add/edit/remove easily later

Ideally, I wanted the data-oriented parts of the articles (names, URLs, etc.) to be centralized and consistent, instead of being copies spread out in different places throughout the articles.


## Data standardization and validation

I also wanted to be able to validate that certain details were correctly displayed and consistent across all the articles. Specifically, musician names should be shown using the same spelling and related information on any pages on which they were mentioned. This was particularly important for Japanese names and titles, as translations to English can differ in certain situations.

Having centralized data with validation checks would also provide a good way to link musicians from any one album to other albums that they participated on. This gave me the ability to create the Musicians Index, where I could link each musician from each album to the other articles that they are mentioned in. This also made the list of Related Albums in each article easier to create.

I needed a database or file system where I could assign a musician key or unique identifier to that musician’s information, specified only once for each musician entry. For example, at a minimum:

-   `musician_key`: [“English name”, “Japanese name”, “instrument”, `website_url`, ...]

Then, when writing my articles, I could use the `musician_key` in a certain way instead of writing out the names, websites, Japanese names, and similar strings in the articles directly by hand. Those details could be inserted later through pre-publishing tools or scripts.

At the same time, I wanted to be able to override certain detail from page to page as necessary. For example, a musician’s primary instrument may be piano but on a specific album they are listed as playing Hammond B3. I wanted to show the musician’s default instrument generally, so that I did not have to type it out each time (“Musician Name - piano”) but override that easily on certain albums when necessary (“Musician Name - Hammond B3”).

Also, by using this data, I would be able to automatically generate an index page with musicians’ names in English and Japanese, with their instruments, website links, and a list of the albums they played on.

Further, with each new album post that I published, I wanted the Musicians Index to be automatically updated using the latest data from the new articles and the centralized musicians’ data. This also gave me to flexibility to design the generated files as tables, lists, with or without thumbnail images, or in any other way (in other words, separation of data and presentation).

In summary, I wanted to:

-   Write in Markdown (plain-text files with simple formatting) with Git for versioning
-   Define a custom data structure for musicians data
-   Store the data in a persistent database or version-controlled data files
-   Generate articles from Markdown using consistent layouts and data
-   Compile indexes from the data and articles
-   Perform analysis and validation of the data used throughout the articles


## The GitHub solution

GitHub was a good fit by providing a Git-based cloud backup and build system integrated with GitHub Pages, a static website publishing system with a Jekyll/Liquid template system. A major change and benefit with GitHub pages was that it allowed me to standardize my Markdown file structure where I could define the data structure I wanted for each “Album” article.

Not only would these files be the source format for my writing, which I had previously copy-and-pasted to Substack manually, now these source files would be directly driving the actual presentation of each published article. No more copy and paste, and no more divergence between my source files and the version uploaded to and edited on Substack.

I wrote a program to import all my posts from Substack to Markdown files, and I created my first GitHub Pages site this way. It was straightforward to link a custom domain `jazzofjapan.com` to the GitHub Pages site.

In addition to the Markdown file format, Jekyll also supported data files. First, I used some CSV files to maintain a database of musicians and other data. This ended up being a very straightforward and convenient solution to the data problem outlined above. With everything available locally on my laptop in Git and backed up on GitHub, all the data and Markdown files were easily versioned and compared to earlier versions. This also gave me more confidence that my files could be easily changed, updated, reverted, branched, and so on. This was also a major advantage over writing in a Substack browser window, where diffs, undos, and versioning and nearly impossible to manage.

The combination of data stored in structured Markdown files and CSV data also made it easy for me to supplement the Jekyll website with custom layouts (for the auto-generated Musicians index page, for instance), and to use other programs I wrote for data validation and analysis.

One constraint with using a free GitHub account and GitHub Pages was that my repository of Markdown, data files, and scripts needed to be public in order to make it available as a public-facing Jekyll website. This meant that all the writing, data, and code was available for anyone to clone or copy easily. I had to be careful to never commit any files to this Git repository that I didn’t want to be available — draft posts, previews, or technical details that I did not want to be stored in the code repository. Keeping everything in a public repo gave me a bit of unease, but fortunately, I found a way to protect the content in a private GitHub repo and to publish the site to my default public repo using a custom GitHub Actions script.

With this solution, I could write, edit, preview, and revise my articles posts on my laptop anytime by using Git, Markdown, and Jekyll. I wrote some code (in Java using Eclipse) to make some things easier, like creating Indexes.

When ready with a new article, I would commit my final version to Git and publish them (push) to GitHub. This would trigger an automatic build and refresh of the website on GitHub Pages that was available through my custom domain. It was a simple and convenient all-in-one solution.


## Results

By moving to GitHub Pages with Markdown:

-   I defined my own data structure and templates
-   I controlled my own versioned writing and data
-   I wrote locally on my laptop using any program (before: Word/Scrivener; now: Eclipse/Notepad++/...) in Markdown
-   I performed analysis on my files
-   I generated indexes/compiled files such as the Musicians Index, a table of musicians to albums that is updated automatically with each new article

The fundamental change from the reader’s point of view was that the _Jazz of Japan_ newsletter was retired, and it was no longer on Substack. _Jazz of Japan_ was now a static website now with no subscription capability (other than RSS) and no subscriber list.

In January 2022, after migrating my newsletter archive (about 150 articles) to my static site on GitHub, I retired the `jjazz` newsletter, closed my Substack account, and continued to publish new articles on GitHub.


## September 2022 - January 2023: Preview posts

I had a long list of albums that I still wanted to introduce, but not enough time to write an article for each that I would be satisfied with. I decided to release articles I would call Previews. These would be very similar to the regular album articles I had been posting, introducing each album with images and audio excerpts, but without any descriptive comments about the musicians or songs. I planned to release Previews in quick succession to the website, to get a page up for each with images and audio, ready to be extended later.

In September 2022, I started releasing Preview articles. I added 53 Preview articles from September 21, 2022 through January 23, 2023.
