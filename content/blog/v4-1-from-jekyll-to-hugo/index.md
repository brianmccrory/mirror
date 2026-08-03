+++
title = "Jazz of Japan from Jekyll to Hugo"
author = ["Brian McCrory"]
publishDate = 2025-03-15
lastmod = 2025-03-15
tags = [""]
categories = ["blog"]
draft = false
slug = "v4-1-from-jekyll-to-hugo"
hiddenInHomeList = true
+++

Jekyll had become too slow as a convenient solution for editing Markdown files on my laptop. With hundreds of articles, thousands of media files (images, audio) files, and several data files, the reloading of the site after a file changed had become extremely slow. Each time a page changed (each time I changed and saved a file in my editor), there was a lag of about 60-120 seconds before Jekyll could reload the page with my changes. This made the writing process very burdensome for certain tasks. It seemed that slowness of Jekyll was a common frustration with Jekyll and large sites.

I had heard that Hugo was a faster alternative, so I decided to run a quick test using my existing Jekyll environment and all my Markdown files. Hugo handled it incredibly well. Page reloads were fast and happened on the order of milliseconds, not seconds. This meant that I could view my changes in a browser instantly, without waiting tens to hundreds of seconds for the site to reload. This was a solution to the exact problem I was having.

Like Jekyll, Hugo uses with Markdown as its default content format, so it did not take much for me to test my Markdown-based writing environment as a preliminary experiment. First, I had to make some general changes to update my customized Jekyll-based environment to a default Hugo-based environment. These initial steps involved things like configuration changes (`_config.yml` to `hugo.toml`, etc.), Markdown file syntax changes (Jekyll/Liquid syntax to Hugo/Go syntax), file and directory changes, and so on. At first, there was a bit of a mess as I had Jekyll and Hugo running in parallel with the same source. This allowed me to compare the two systems side-by-side with the same source data, and decide if a Hugo-based site was interesting, nice to work in, and worth the migration effort. Having Hugo run on an existing Jekyll project worked up to a point, but eventually, after I decided to dig deeper with Hugo, I created a new repository for my Hugo site and copied all my content into the new project.

The major change was customizing the Hugo theme to match the Jekyll layouts and formatting I had been using, so that I could continue copy-and-pasting rendered text from my browser to the Substack editor. I would do this for each new or updated article page and the resulting generated index pages. Since 2022, I was no longer writing and editing articles in the Substack editor or in a writing tool like Scrivener because I wanted to write, save, and manage versions of files using Markdown and Git.

From a _Jazz of Japan_ reader’s perspective, nothing really changed. The newsletter and archive were still on Substack, and the generated index pages were still on the subdomain and GitHub pages. But my writing environment, based on Markdown files rendered through Hugo instead of Jekyll, had improved dramatically.
