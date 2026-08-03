+++
title = "Offline-first writing"
author = ["Brian McCrory"]
publishDate = 2026-04-29
lastmod = 2026-04-29
tags = [""]
categories = ["blog"]
draft = true
slug = "v5-2-offline-first-writing"
hiddenInHomeList = true
+++

## 2018-2019: Writing in a browser

When I started this project in early 2018, I created articles by writing directly in the browser. In the beginning, I would type directly into the WordPress editor running on my laptop and then upload files to WordPress running on Amazon Web Service and Google App Engine at different times. Later, when I switched to Substack, I would type directly into their web-based editor app, edit, and publish through Substack. The final versions of my work were saved on Substack servers. The only way I could get the latest version of an article was to load the webpage and copy the text or use Substack’s HTML-formatted exports.


### A manual process

I arranged my articles in a simple, specific layout that worked well with my one-article-per-album format: I had certain title and body sections, headlines, fonts, formatting, images, and audio placed where and how I wanted them to appear. It was more or less a template that I could copy for new articles. For consistency, I would copy my previous article and replace the details for each new article.

While writing the article text, I also needed to upload images and audio files through drag-and-drop from my laptop to the browser, placing them exactly into the text where I wanted them to go in WYSIWYG style. With WordPress, I used templates and plugins, and I could access the database to view and edit data. With Substack, it was like a content management system running in the browser. To get a detailed view into my source writing, all I could do was export my data as HTML files from Substack. But with both WordPress and Substack, I was still typing text into a browser, and all formatting, media, and organizational elements were mixed in with the text in a way that I could not precisely define, structure, or standardize (by using a markup language, for instance).

This browser-based environment for article writing and editing worked, but it made my writing process dependent on specific tools and conditions. These include the features, limitations, and quirks of WordPress, Substack, the OS, the browser, internet connections, and so on.

In the early phases of this project, I was focused with getting things out in a reasonable format and at a steady pace. With those priorities, a browser-based writing process was a natural way to start and maintain for a while. I got used to it, but I didn’t like the repetitive manual steps that were part of the process. Making widespread changes was daunting, so performing tasks like re-uploading images, adding sections, or updating the layout for every page would not be easy. For example, if I wanted to add a link to the footer of all pages in my Substack archive, my only option was to load, edit, and update each page one by one in a browser. To update hundreds of pages manually takes considerable time and effort and is an inherently error-prone process.


### Browser-based editors

I never liked writing directly into a browser. In a positive light, browser-based editors are convenient and powerful, and the slickness of some UIs can almost create a feeling of encouragement, like there’s nothing between you and your writing.

On the other hand, typing in a browser can be frustrating. If your fingers are used to certain shortcuts or keystroke commands common in other programs, you have to readjust and remember that these keys may be mapped differently in the browser, or in the custom editor app running in that browser. (_“Grrr... No, I don’t want to print the page/save the html/open a new browser window...”_) Relearning key shortcuts and internalizing them can be hard to do when you are focused on writing and muscle memory drives a lot of your automatic typing.

A browser-based writing environment can be especially annoying when the text grows long, goes through many edits, or is completely rewritten. If you want to revert changes, the undo command can only do so much, and it’s difficult or impossible to compare the current version with what was there before.

Plus, it’s frustrating to have a browser freeze or crash in the middle of writing, or lose internet connectivity, and you don’t know how much of your text, or which version, was most recently saved. Just the possibility of that happening while you are writing can create a subtle state of underlying anxiety, a less than ideal state when you want to have a good, relaxed writing session.

Substack included a rudimentary version history feature in their editor, but the tool did not include a way to see detailed differences or compare versions. You could only go back to recover a previous version from a long list of auto-saved versions, which could be a minimum safety net in case of emergency, but not as useful as a real version control system.

Furthermore, trying to write an article by typing directly into a browser somehow feels more ephemeral, as if writing an off-the-cuff social media post that you are in a hurry to get out, something that you may not consider to be important as a long-lived statement. To me, this is different from fine-tuning a piece of writing by spending time (days) proofreading, editing, and finally publishing something in a finished form that you are happy with. A browser-based editor is convenient for some things, but not a great place for such a deliberate writing and editing process.


### Writing while online

Using a browser-based editor for writing also means that you need to get online and stay connected to the internet. For example, to load the Substack editor, and to load any drafts or previous articles, you need to log in to Substack in a browser. As you write, Substack saves your changes to their online system, and this also requires uninterrupted internet access. Similarly, uploading images and audio files to include in a draft is dependent on internet access.

It wasn’t that internet access was a problem for me, since most of my writing was done at home anyway. But I didn’t like the fact that having internet access was a necessary condition for writing, revising, and previewing drafts. Plus, being always online, with the perpetual consciousness of having instant access at your fingertips to web searches, email, and alerts is a distraction that can interfere with deep thinking.


### What I wanted instead

Eventually, I wanted to improve my writing environment in these ways at least:

1.  Use a dedicated program for writing, instead of typing directly in a browser
2.  Not be dependent on an internet connection to write and update articles
3.  Have a more convenient way to insert and arrange images
4.  Use version control for the source of my articles

At various times, I had used programs like Word, Scrivener, Notepad++, Eclipse, and Emacs to write drafts and paste them into the WordPress or Substack editor. A constant problem with this was that it was too easy to make simple edits and revisions directly in the browser to view them in context. But, when doing this, I needed to remember to keep my source material simultaneously updated. The proper alternative was to return to my source text, revise it, and then copy-and-paste it all back to the browser when done, but this is a repetitive process that quickly becomes a hassle if editing continues for a while.

Part of these goals was to be able to choose the best offline writing environment, to switch tools anytime with minimal impact, and to not be tied down to any specific online browser-based editing tool with all its limitations.

---


## 2019-2026: Writing offline, posting online

As my list of published articles was getting longer, I started to use standalone programs to write and manage my articles offline, outside of browsers, and independent of any web-based apps. I would write in text files, and when I was done writing and editing, I would copy the text into the browser-based editor for final formatting, adding images, and publishing. This way, I knew where my latest version of each article was stored: They were stored as text files on my laptop and backed up as a complete folder. I just needed to remember not to edit my Substack version without first editing or simultaneously updating my original text stored in a file.


### The copy-and-paste option

Copy-and-pasting formatted text from my source version into a browser-based editor was a manual step, but it was easy, and I could repeat this each time I edited my text.

A major benefit of this copy-and-paste method is that my writing is not located primarily in, or owned by, any one online platform or service. The latest version of each article is always saved in a text file (my authoritative source of truth) that I own and manage with complete freedom. Plus, this includes the ability to have a complete version history of changes made to each file. Using a version control system like Git gives you the convenience and reassurance of being able to write, revise, and edit on a local machine (online or offline) through simple commands to commit, revert, see differences in detail, and review changes between any points in the version history.

One big problem with this process involved handling the images that I was inserting throughout the text. For each image, I needed to drag and drop it into the editor, one by one, and adjust the position in the text. If I needed to revise the text, I either had to make each change in two places, leaving the images in place while carefully synchronizing the browser text and my source text, making edits in both. Or, I would have to copy my source text after editing it, paste the whole article back into the editor, and then insert and arrange each images again, since the copy-and-paste would overwrite the images that were inserted and arranged previously.


### Managing versions and revisions

For writers who want to avoid writing in a browser-based editor, writing in a native program (like Notepad, Word, or Pages) and pasting to Substack when ready is a good option. But this creates some new problems, or questions to think about at least:

1.  What is the source for the latest version, a local version on your computer or the published version on Substack?
2.  How can you compare versions?
3.  How can you manage updates to the current working version versus the current published version?
4.  How can you see changes between revisions, or revert to a previous version?

These questions illuminate one big drawback of the copy-and-paste method. Now there are two copies of each article - the online version and your original source version - and they need to be kept in sync with any changes, whether they are small edits or large rewrites. (That is, unless you decide that the online version is frozen, reflecting a point in time, and should not be updated again after being sent out. If so, what if you want to fix a typo, add something, or revise the article? Do you update the existing article, or republish a completely new article and leave the original article as-is?)

On Substack, in order to find and view differences between my current version and the published version of an article, I had to find a way to compare my source text against Substack HTML-formatted export files. This (comparing the two versions) is a problem that can be solved through programming, and it works to some extent, but it’s not a great long-term solution.


### Writing in Markdown

In 2022, I began to write and save my articles as text files in Markdown format that I could [publish online as a Jekyll static site](/blog/v3-0-github/).

This helped me with some of the goals listed earlier:

1.  I could write and edit offline
2.  I could use any program to write
3.  I could standardize layouts and automatically generate indexes through Jekyll templates
4.  I could use Git for version control

In 2023, I [restarted publishing on Substack](/blog/v4-0-substack/), but I continued to use Markdown as my source writing format. I would copy-and-paste drafted and completed articles from my local Jekyll instance (later Hugo, and then Org mode exports) into the Substack editor. This worked well for formatted article text, but images still had to be dragged and dropped individually... still a drag.

---


## 2026: Publishing through an API

In February 2026, I [migrated the newsletter to Buttondown](/blog/v5-0-buttondown) and was now able to create articles through an API. I no longer had to copy-and-paste formatted text from an HTML page generated by Hugo or Emacs into a browser to create an email or article, since Buttondown supports Markdown formatting natively.

This was one of the biggest improvements to my writing process up to this point. I could now manage writing, edit and arrange images, and update layouts entirely on my laptop by editing Emacs Org mode or Markdown files. I could also stay offline for much of this, if I needed to. (The trade-off was not seeing a real-time preview of your text exactly as it would appear in a browser, but this is not necessarily a bad thing during the writing process.)

I only needed to interact with the Buttondown publishing system through APIs when I was ready to create a draft, upload images, or preview or send an email. Similarly, it was just as easy to update the web archive for a previously sent email, or even update all articles through automated scripts.

With this change, I could maintain the official latest version of each article on my laptop and in source control (online and offline) in a structured markup format (Org mode or Markdown) that I could easily compare to previous versions that I had saved (committed). I could also compare my source versions against the currently published versions stored on Buttondown and available through their API. This gave me the ability to determine if there were any differences between my latest version and my published version, to view the scope and exact details of any differences, and to update the published version with my latest changes easily when I need to.

A minor detail: Since I was saving source files in Org mode, and Buttondown saves Markdown, I would need to convert my source from Org mode to Markdown to produce a useful `diff` (a line-by-line comparison) between the two copies, but this is a straightforward transformation that can be automated through tools. I was already using a wrapper script to integrate my environment with Buttondown’s API, so this transformation became a preprocessing step, a part of the pipeline that was invisible to me. This was the same transformation that I used to upload drafts to Buttondown originating from my Org mode source files, so it was a natural fit for my `diff` function.


### Current writing environment

Now I am much closer to my ideal writing environment compared with where I started.

As a step-wise process, in order:

1.  **Write:** Write, save, and edit text files with formatting markup (Org mode/Markdown)
2.  **Compare:** Diffs, version control, and backups with Git (repeat 1-2)
3.  **Upload:** Create and update drafts through Buttondown’s API
4.  **Preview:** See previews in Buttondown’s web UI (repeat 1-4)
5.  **Finalize:** Commit final changes
6.  **Pre-publish:** Update indexes and audio mixes using the latest markup and data files (automated through scripts, GitHub, and Hugo)
7.  **Publish:** Publish articles (send emails) through Buttondown’s web UI

Other supplemental steps involve:

-   **Images:** Crop, resize, and add a reference in the relevant text file for each image placed inline with the text
-   **Audio:** Select a track to highlight and add its file path to the text file as metadata, used by a script to automatically create the excerpt and add it to the proper audio mix file
-   **Code:** Scripts and supporting tools, including a wrapper for Buttondown’s API
-   **Data:** Files for consistency, correctness, and centralization of data including album release details, English/Japanese spellings, instruments, websites, venue locations, statuses, etc.
-   **Versioning:** The latest and previous versions of each file are saved in Git, making it easy to view, compare, revert, branch, backup - all the standard benefits of a robust version control system

The largest benefit of this writing process is **escaping browser-based writing**: I no longer have to write, edit, and revise article text, upload images, adjust formatting, or rearrange layouts in the browser. Compare this to before, when I had to copy formatted HTML into the Substack editor and drag images and audio files in one by one, and repeat this tedious process each time I wanted to repaste modified text into the browser. (Otherwise, I have to carefully keep both copies in sync whenever I changed something, doubling the work required for editing).

Another benefit for me is having the option to **stay offline** for most of this. My writing process is mostly disconnected from the internet, and I can write, revise, and compare versions locally on my laptop. I only need to be connected to the internet to preview or publish articles, or to perform remote Git operations like pushing a change to save a backup.

The last big benefit I’ll mention here is that I can **easily update existing articles**. For example, if I find a typo in an article, I can fix that in one text file and update the online copy through Buttondown’s API - no browser required. Or, if I want to update a name or link that is used in different articles, I simply need to update one line in a data file and run a script to update every article that contains that term. Even if I want to update every published article at once, say to change the general layout or something in the header or footer, I can do that very easily by using a script that automatically runs through all articles and updates each one through an API call. The best part is that I can stay in my offline editor and update my changes through an API, never needing to switch to a browser. This type of widespread change would be incredibly burdensome and time-consuming with a browser-based editor that requires changes to be made manually, one by one, and has a much larger potential for mistakes. Also, with version control fully integrated in my environment, I can review each change in detail, `diff`-style, before I commit to saving or publishing that change, whether it’s a typo fix, a brand-new article, or an extensive change.
