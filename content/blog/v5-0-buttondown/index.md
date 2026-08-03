+++
title = "Jazz of Japan on Buttondown"
author = ["Brian McCrory"]
publishDate = 2026-04-15
lastmod = 2026-04-15
tags = [""]
categories = ["blog"]
draft = false
slug = "v5-0-buttondown"
hiddenInHomeList = true
+++

## February 2026: Buttondown migration

I had been considering alternatives to Substack for some time, and eventually I decided to give [Buttondown](https://buttondown.com/refer/jazzofjapan) a try (this link includes a first-month discount for you and a referral bonus for me). Why was I considering a move? Well, for a long time, there were elements of Substack that I was unsatisfied with that I may describe later (there is no shortage of articles and opinions on the web on this topic), and this feeling was increasingly bothering me.

Buttondown was attractive for a number of reasons: their focus on newsletters, support for Markdown format, having an API, and their size and goals as a company. On the downside, running a newsletter on Buttondown would no longer be free as it was with Substack (which was not really free, since they were taking 10% of money earned through paid subscriptions while inserting their ads, upsells, and branding as they wished). Still, the advantages of Buttondown, and the independence and control that I would regain by moving off of Substack, were worth it to me, and it’s good to pay for products that are worth it.

I signed up with Buttondown and setup my new _Jazz of Japan_ newsletter there, paying $290 USD for one year to get the features I wanted. I wrote a program to automate the process of transforming my Org mode articles to Markdown and uploading them to Buttondown through their API. Using my archive of markup files and images, a Python script, and Buttondown’s API, I imported my complete archive and subscriber list to `buttondown.com/jazzofjapan`.

As an alternative to programming scripts, Buttondown also provides a command-line interface, but I was already using my own scripts for tasks supporting my writing, so I continued using scripts to integrate with Buttondown’s API. For writers who want to import their newsletter archive to Buttondown more easily, there are ways to import a Substack archive that don’t require any programming or using APIs, up to and including personal concierge support from Buttondown.

Because all of my 350+ articles were already in markup format, using Buttondown’s API to import my newsletter to their platform was straightforward. Uploading my articles directly through an API meant that I did not have to export/import articles from Substack to Buttondown. This gave me greater control and visibility into how my articles would be transformed during the migration.

After verifying that everything was uploaded and appeared to be in a good state, I updated my DNS settings to move my custom domain `www.jazzofjapan.com` from my Substack publication to my Buttondown newsletter and archive. Without a custom domain set on Substack, my Substack publication was reset to the default domain, and my Substack archive was still available at `jazzofjapan.substack.com`. To avoid having my web archive duplicated, I unpublished all my articles on Substack so that they were solely available on through my Buttondown archive. I had been using the same custom domain since 2022, so moving my archive of 350+ pages from Substack to Buttondown did not affect SEO or Google search results, as the `www.jazzofjapan.com` domain remained the same.

There was one difference: The format of individual article URLs changed from `/p/slug` to `/archive/slug/`. But, not to worry: the `/p/` URL versions are still supported by Buttondown as aliases or redirects for `/archive/`.

I was now up and running on Buttondown. I stopped sending newsletter emails updates through Substack, and my next newsletter email was sent through Buttondown with no problems or interruption.


## Results

-   Buttondown was now the platform I used for newsletter emails, the web archive, and subscription management
-   The newsletter and archive were completely migrated and no longer on Substack
-   The newsletter and archive were still on <https://www.jazzofjapan.com> which now pointed to Buttondown servers
-   Emails were now sent from my custom domain `jazzofjapan.com` instead of `substack.com` and reflected in the sender’s From: field
-   Both Substack and Buttondown use Stripe as their payment platform, so paid subscriptions continued, and it was just as easy as before for newsletter subscribers to upgrade to a premium subscription if they wished.

    There was a little bit of work required to get Substack support to disconnect Stripe without canceling my paid subscribers. Once this was done, no paid subscribers were affected by the change to Buttondown. There was one exception: Paid subscribers who upgraded on Substack using iOS in-app payments were managed through Apple, so their payment details could not be transferred to Buttondown through Stripe. Buttondown support was great in providing a quick workaround for this, which involved giving those iOS-based premium subscribers a free trial month, after which they could add payment details through Stripe when their trial ended.
