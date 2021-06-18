---
layout: post
title:  "The Great Migration"
date:   2021-06-18 12:34:46 +0000
categories: jekyll update
---

I am in process of migrating my blog.

Why? Previously I've been using a custom built system to host my blog. It's written using Python3 and Flask, runs in a docker container, sits on a rented virtual server and has requests fed to it via nGinx.

That's a lot of work for a glorified website. And not that glorified, believe me.

I built it for a reason, of course. That reason was to demonstrate the idea of "security through entrapment" so it was filled with lots of weird little tripwires and pit-traps for people to fall into. But with the source in github, a database on the server itself, pipelines to push updates, the whole thing just became completely unwieldy. Four different technologies just to support one site. Not to mention the looks of the thing. I am *not* a front-end guy. And while it didn't look bad, changes to it were almost impossible. I have no eye for such things.

So I started looking into alternatives. I considered Ghost for a while. Open source blogging platform gives me a bit of a nerd-on after parts of my past life dealing with terrible commercial efforts and WordPress. But again, required hosting. Github Pages was something I wanted to exploit. I mean these guys are cool enough to give us free space. Why wouldn't I use it? 

There are a couple of projects dedicated to running ghost in Github Pages, but it didn't eliminate one thing that always bothered me about these packages. Why require a database at all? Storing text, images, etc, should *not* be this hard.

My attention was drawn, as it had been before, to Jekyll. And here we are. It's pretty sensible, I guess, rendering static pages. After about an hour of wrestling I got this whole thing set up with a theme I like. 

Now there's just the task of my old blog and migrating some of the blog posts here. Not all of them. Some of them are out of date. Some of them are stupid. And I wanted to try a different style of writing. More free. Closer to mirroring an internal thought process. That way I can blog, however shortly, on all matters that strike my attention. Before I focused on InfoSec, and that will likely be a heavy focus here too. But maybe music. Gaming. Politics. Maybe this will end up as my version of Anorak's Almanac.
