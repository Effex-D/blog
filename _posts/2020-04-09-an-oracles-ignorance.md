---
layout: post
title:  "An Oracle's Ignorance"
date:   2021-04-09 14:34:46 +0000
author: Effex
---

Today I am writing a two part blog. I will probably write and publish both blogs today, but people have short attention spans when it comes to reading (but can binge Netflix like a beast) so I am splitting it in half.

In the first part I want to talk about Oracle, OCM and TLS.

Oracle, for the few (or none) of you who don't know, are an American tech company who specialize in database management and the systems that connect to such data stores. In theory.

In actuality, they run a business model similar to that of Electronic Arts. Find promising up-and-coming developers with an exciting product. Make said developer and offer they can't refuse. Purchase company and product. Drain product for all value. Once product is drained, discard.

If you'd like proof, just check out the acquisitions page Just try not to fall for their marketing hype.

Oracle have no fire behind their development. No real interest in it, other than the min/maxing of profits. As such, Oracle technologies lag behind the latest innovations from other, similar products.

And I want to talk about one of those products today.

OCM. Oracle Content Management.

We all know of blogging platforms. Mortals have access to Wordpress and Medium and Blogger. One nerd even uses [Se]m[bl][en]ce. We dumb them down to blogging platforms, but what they actually represent are Content Management Systems (CMS). A way for non-tech people to manage content inside a safe system, and still publish with a specific style and branding. Huge amounts of websites are hosted using these systems, with Wordpress alone comprising 60.4% of the market share of CMS systems (and 33.5% of all websites. Literally. Of all websites, a third run Wordpress.)

But there's another, invisible layers. Sitecore. Pantheon. You're likely never to have heard of these. They are marketed to people who run companies operating in the tens to hundreds of millions. They don't want to be dealing with your piddly little $10/month website.

OCM is Oracle's attempt to step into this market. Though I feel that is an inaccurate statement. It was once Oracle's newest attempt to suck some money from the teat of a business they care precious little about.

OCM started life in 2007 as the product compendium. A Content Marketing Platform, basically a CMS tilted towards marketing (and what part of the internet, these days, is not?). Compendium was purchased in 2013 by Oracle, and the draining began.

Compendium was not a great contender to begin with, though Oracle's habit of halting development until legally required has made things far worse. But instead of going through all its problems here, I want to talk about one specific problem.

Compendium does not natively support HTTPS.

It offers no support for obtaining certificates. Or even uploading your own. The official documentation for OCM states that HTTPS function is provided through a reverse proxy. Which sounds fancy, doesn't it?

A reverse proxy is literally another machine, that converts the upstream traffic to HTTPS.

You can only encrypt your traffic in OCM by using an expensive work-around that requires technical resources. On a machine that could be used to host the content, in lieu of Compendium/OCM.

By comparison? Wordpress, Blogger, Medium, all offer TLS encryption as standard.

Because the year is 2020.

P.S: As an ironic aside: check the link above. Oracle's website runs TLS, so they clearly see the value of it. Just not for other people.

P.P.(hurr).S: Still have an attention span? Want to keep reading? Cool. Go here
