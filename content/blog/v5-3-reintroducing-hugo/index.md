+++
title = "Jazz of Japan reintroducing Hugo"
author = ["Brian McCrory"]
publishDate = 2026-07-19
lastmod = 2026-07-19
tags = [""]
categories = ["blog"]
draft = true
slug = "v5-3-reintroducing-hugo"
hiddenInHomeList = true
+++

2026-07-21 (JST):

-   changed buttondown payment plan (stripe) from yearly $290 to yearly $90.
-   updated favicons/manifest (in static/) based on <https://favicon.io/favicon-converter/>

2026-07-20 (JST):

-   sent first email hitomi-nishiyama-songs (dated 7/19) through newsletter.buttondown.com with hugo as the website.
-   need to figure out how to change relative urls in body (markdown) to full urls for buttondown api update
-   and description
-   automatic sitemap: <https://www.jazzofjapan.com/sitemap.xml>
    -   submitted to google search console
-   now that I have tags for all musicians, english and japanese, the sitemap is large (thousands)
-   mirror site: <https://mirror-3fn.pages.dev/>

2026-07-19 (JST):

-   moved buttondown domain to newsletter.jazzofjapan.com
-   set hugo site (on cloudflare) to www.jazzofjapan.com
-   updated canonical urls on ~10 emails so that existing links redirect properly to new domain / url format
-   turned off archive on buttondown (entirely replaced by hugo so that there are not two sources of archives, and so I can remove all imported emails from buttondown)
-   removed extraneous links from buttondown (Archives, About, Audio, Indexes, RSS)
-   turn off Search on Buttondown navigation menu
-   change About link on Buttondown navigation menu

To do:

-   fill out buttondown descriptions somehow
-   check related for albums/extras that it works based on related tag (must in front matter before [sections] and [[ lists ]
-   **\*** make sure all new buttondown emails contain canonical url
-   **\*** for the buttondown subscribe page - change the title on the upper left ( add “Newsletter”?) or change the link to go to www instead of newsletter
-   extend the description
-   check all http/https forms (www, newsletter, brian, docs, about, etc)
-   check all urls are canonical form with “/slug/” style slashes at end (and look for bad links)
-   MONITOR GOOGLE SEARCH CONSOLE &amp; ANALYTICS for any significant changes
-   check redirects, website tools, seo tools, etc for problems
-   test all links in all sent newsletter emails to make sure the redirects / canonical urls (set on buttondown) work properly
-   remove all imported archived (not sent) emails/images in buttondown
-   remove about/index/audio static pages from buttondown (and make sure links are accurate)
-   downgrade or remove ’archive’ from buttondown (but need subscription page)
-   consider using hugo relref: or other file existence/safety checks

To check:

-   apex domain redirect working for both http/https? jazzofjapan -&gt; www.jazzofjapan.com

Major changes:

-   issues are removed from footer and end-user display (should i maintain these, as internal codes/ids?)
-   urls are “flat” (without _archive_, _albums_, _clubs_, etc) but redirect rules are in places
