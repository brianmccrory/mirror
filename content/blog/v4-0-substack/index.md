+++
title = "Jazz of Japan on Substack + Markdown"
author = ["Brian McCrory"]
publishDate = 2023-05-03
lastmod = 2023-05-03
tags = [""]
categories = ["blog"]
draft = false
slug = "v4-0-substack"
hiddenInHomeList = true
+++

## May 2023: Moving to Substack + Markdown

Now that the entire system was stored in GitHub as articles, images, audio, layouts, and code, I returned to Substack to reintroduce the newsletter functionality and update the website’s look and feel.

While the GitHub/Jekyll-based version was functional and straightforward, there were some limitations that I was facing. Aside from social media promotion (that I had tried before, and decided to avoid), there was no convenient way to share articles more widely, such as with a newsletter.

Considering relaunching the newsletter, I was being drawn back to Substack’s ease of use, clean interface, and tools. One of the biggest benefits of using Substack was that it was such a convenient place to write. The interface was clean and welcoming, the tools and settings were simple and pared down, and there was a wealth of support and an encouraging community. The system just seemed to make you want to write.


## Moving from GitHub to Substack

As part of a test of how I could integrate Substack with my Markdown files, I began by importing all my files from GitHub pages to Substack. It started off well, so I tentatively shut down the GitHub Pages project and continued to send articles using Substack for the newsletter and archive. I also moved my custom domain `jazzofjapan.com` from GitHub Pages to my Substack publication.

There was one important difference compared with how I had used Substack before. This time, I would use Substack for the newsletter and website, but I would continue to write and maintain Markdown files and data files on my laptop, as I had started doing with the GitHub Pages version. I continued to store all these files in Git and back them up on GitHub. The reason for this was to maintain control over the authoritative content that was the text for my articles, data, images, layouts, templates, and so on. I would not have to worry about using Substack’s editor window in a browser to write, edit, or make changes, without knowing exactly what had changed from version to version.

In effect, I was maintaining two systems for writing and publishing. I used Substack to handle the new v4.0 website with public articles, subscriptions, and newsletter emails. At the same time, I used Markdown and Git on my laptop for writing, data, and scripts for validation, templating, automatic indexing, and other tools.


## Writing in Markdown and publishing on Substack

Using Markdown plain-text files, my files were now my source of truth, my latest versions with a complete version history. I also now had a simple way to convert them to Substack articles each time I completed a new article, changed an old article, modified a layout, etc. This manual import to Substack was simply a copy and paste of the rendered HTML from one browser tab (Jekyll on localhost) to  another (the Substack editor).

Also important, I could write freely in version-controlled plain-text Markdown files, on my laptop, with any program I wanted, like Word, Scrivener, Notepad++, Eclipse, Emacs, etc. Then, using Git, I could back up those source files easily and compare differences between versions or create branches for different projects.

With Jekyll running on my laptop, it was easy to incorporate common sections into my articles. I used these sections to include the album’s musicians, audio, video, and links. I could combine my free-form writing with data-driven portions. For example, I could transform keys like `fumio-karashima` into text like “Fumio Karashima (website) - piano” and include the Japanese name for each musician. I could use a standard layout by using my templates, data, and scripts to format my articles consistently in the way that I wanted, and I could change those layouts and templates later, easily, if I wanted to.

Finally, when viewing Jekyll’s locally rendered Markdown page in a browser, I could cut and paste the formatted output directly into a Substack editor window. As a manual process, this worked conveniently but not completely: Article attachments like images and audio files needed to be dragged into the Substack editor, one by one, and moved within the text to the location I wanted them to appear. Since my articles usually contained many images and an audio file, this was a problem that I wanted to solve someday. I wanted a solution where, ideally, the whole formatted article, with images and audio in their proper places, could be uploaded through a public Substack API, but Substack did not offer this.

With all of my Markdown files stored in Git on my laptop, it was also reassuring that I had a cloud-based backup on GitHub for everything with a complete version history. Plus, I could clone that repository anytime on another machine. This would be a lifesaver in case anything disastrous should happen to my local copy or the copies that I was uploading to Substack.


## A problem with the dual system

One problem with this dual approach of maintaining my source files and copying them to Substack was the potential for the two copies to diverge. How would I know if I accidentally changed something in the Substack editor without updating my local copy, or vice versa? I wanted to keep the files synchronized in one direction, from Markdown to Substack, and be aware if any differences arose later.

My policy was to always consider my Markdown files as the authoritative source of truth, in terms of the latest versions of my writing. This is because I completely controlled my Markdown files, but once I uploaded copies to Substack, they were partially out of my control (and could be changed by bugs, hacks, new features or updates, policy changes, etc.).

Of course, since Substack was hosting my newsletter archive and sending my emails, they always had the ability to do whatever they wanted to my articles, without my knowledge or consent. They could insert their own branding, advertisements, and recommendations in the space above, below, or around my writing (let’s wait and see if ads are ever placed within the text of articles!). They could add prompts to upgrade, to pledge support, to download their app, and promote any of their new features. Some of these have already happened.

To address the problem of the text of my articles diverging between my source copies and the Substack copies, I created a program to check for differences based on the Substack exports, which I would diligently download at least once a month. This worked well enough to identify visible differences between the two versions.


## Results

By moving to Substack with Markdown, I combined the advantages of my Markdown- and Git-based authoring system with the functionality of a Substack newsletter and archive like I had previously used in an earlier version of this site.

After restarting the newsletter in May 2023 and importing all previous articles (excluding album previews), I continued to test new Substack features like newsletter sections, paid subscriptions, and additional newsletters, but I usually came back to my guiding principle of “simpler is better”.

In addition to continuing to write new Albums articles, I also started to publish articles in the Clubs and Guides categories. Paid subscribers also started to generously contribute to my newsletter, which made me extremely happy and boosted my motivation to keep it going with regular and better updates.

The fundamental change from the reader’s point of view was that the _Jazz of Japan_ newsletter was restarted, and it was back on Substack with the complete archive. I continued to use Substack for _Jazz of Japan_ until February 2026, making various changes to my writing environment throughout.
