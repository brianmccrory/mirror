+++
title = "Jazz of Japan from Markdown to Org mode"
author = ["Brian McCrory"]
publishDate = 2025-07-15
lastmod = 2025-07-15
tags = [""]
categories = ["blog"]
draft = false
slug = "v4-2-from-markdown-to-org-mode"
hiddenInHomeList = true
+++

My goal at this point was to simplify my writing environment by moving from Markdown files to Org mode files. Initially an exploratory project, I wanted to see what the effort would be to move to Org mode, and if there were enough advantages for me to write and save files in Org mode markup instead of Markdown markup. I also wanted to return to an Emacs-based writing environment, and while Emacs supports general-purpose formats like Markdown very well, Org mode goes further, as it is a native Emacs format and is more tightly integrated.

Formatting is similar for Markdown and Org mode files, and the syntax can be converted easily. For example, Markdown uses `#` for section headings, `*` to wrap italics, `**` to wrap bold, and `[ ]( )` for links. Org mode uses `*` for section headings, `/` to wrap italics, `*` to wrap bold, and `[[ ][ ]]` for links.

```nil
Markdown example:                          | Org mode example:
-----------------------------------------------------------------------------------------
# First level                              | * First level
                                           |
This is *italic* and **bold**.             | This is /italic/ and *bold*.
A [link](http://www.example.com/) in text. | A [[http://www.example.com/][link]] in text.
                                           |
![](/path/image-file.jpeg)                 | [[/path/image-file.jpeg]]
                                           |
## Second level                            | ** Second level
...                                        |  ...
```

First, I converted hundreds of individual Markdown files (one per article) into Org mode format. This can be done automatically by using the standard utility `pandoc` for document conversion. I also grouped the individual files (one per articles) into just a few large, topic-based files, with a separate top-level section for each article. For example, I now had `albums.org`, `clubs.org`, and `guides.org` (and a few others) instead of hundreds of files with filenames like `article-title.md`.

This conversion to Org mode allowed me to improve my copy-and-paste flow from HTML to Substack, my manual import process that I followed when I needed to create or update a Substack article. Previously, I needed to copy-and-paste a Hugo-generated HTML page into Substack’s browser-based editor (omitting images, which had to be handled separately). This required me to run Hugo to generate the HTML, something I had been doing for a while and was not particularly a problem. Still, I thought it would be nice to eliminate an extra dependency and link in the writing process if I could:

```text
BEFORE: Markdown file -> save --> Hugo (running) -> HTML -> Substack
AFTER:  Org mode file -> export ------------------> HTML -> Substack
```

With Org mode, instead of running Hugo to generate HTML, I could export Org mode files from Emacs to HTML directly with a few keystrokes. I could even continue to use Hugo since it works with both Markdown and Org mode files.

Org mode in Emacs also includes the benefits of better document navigation, subtree folding (section collapse/expand), integrated status and task tracking, and exporting to a variety of formats. For people who are familiar with Emacs and used to writing in an environment with Emacs commands, it may feel more natural to write in Org mode instead of Markdown, especially if you are already using Emacs or Org mode for other things.

Fortunately, it is easy to switch between Markdown and Org mode depending on the situation, since they are both markup languages based on text files and a simple formatting syntax. As a general-purpose documentation format, Markdown definitely has its place, and I am comfortable switching back to Markdown formatting for quick notes and certain cases, useful for its simplicity and ubiquity. Within this project, however, all Markdown files were converted to Org mode.

After this move to writing and saving all my source files in Org mode, I no longer had to run Hugo on my laptop, as Hugo was no longer an essential part of the copy-and-paste pipeline to Substack. I also found it convenient to have all of my articles stored and organized in just a few Org mode files, even though the files were large, nearly 20,000 lines in one case. I haven’t had a problem with Emacs handling these large files well, and with section folding, document navigation, search, and other useful features, it’s a change that I’m happy with.
