---
title: "Bookstack and Almanac"
date: 2024-06-03
author: Effex
tags: []
---

I think this is the end of my Jekyll-based blogging.

And it's pretty much my fault. I built the blog using github pages with Jekyll because it seemed easy, it was free, and it allowed me not to have to deal with anything on the UI side after my... interesting experiments with Semblence, my own blogging platform built with Python and Flask.

It was simple, really. Required no database, had posts as files. But it became... complex. Not the system itself, but the workflow of the system Here's how my typical blog post flow goes:

1) Create blog post using script which creates an md file in the posts folder.
2) Add the newly created file to the git repo.
3) Open the created file in a text editor and write the post in .md format.
4) Save the file and add the changes to git repo.
5) Commit the changes to the git repo.
6) Push the changes to git source origin on Github
7) Wait for the pipeline in Github to push the changes to the page.
8) Notice an error in the page, return to step 3 to correct.
9) Repeat steps 3-8 approximately 5 times.
10) Admire blog post.

Parts of this are even slowed down by the fact that only *recently* I activated SSH pushes to Github, so had to input a password, and later an access token, to get my posts to where they needed to go.

This is not a convenient workflow, and I wonder how much of my malaise about blogging comes from this work flow. It's impossible to enter the "flow state" of actually writing when the process is punctuated in such a way. As someone who has written, and as someone who has coded, writing should not be treated as code.

And then, almost by accident, I stumbled across the solution.

I was looking into replacements for Confluence, now that Atlassian has gone Full Cloud No Server in an attempt to force all their users into one, conveniently sortable, searchable and AI accessible, mess online. Several of the tools I found were... crap. Or giant.

But Bookstack took my fancy. As it is described on the website:

>> Simple & Free Wiki Software
>> BookStack is a simple, self-hosted, easy-to-use platform for organising and storing information.

And it isn't wrong. It has an installation script for use on a plain Ubuntu installation which installs the Bookstack. It's free and open source, searchable and configurable, uses markdown, etc It *is* built using PHP which I'm struggling with, but in general it feels very stable and useful.

My favourite part is how data can be stored. Layers of storage. Shelves, which contain books, which may have chapters and pages.

Something about this set of controls appeals to me.

But I'd need to architect it. I can't just dive in and start dumping stuff there. Even though that's exactly what I did in the testing environment I have here in my apartment. I have, however, been considering running it in a VPS somewhere, either using Hetzner like my other systems, or using something like Cockbox. Or I might just throw it into the free Google VM. After all, I've still not made a solid decision which cloud provider I'm heading towards. AWS and Azure seem to be the most popular options with GCP growing but...

They're all evil.

But it leans into an earlier post, where i have the "almanac." A collection of my thoughts, my experiences, my knowledge, on whatever subject I choose to share, that can be browsed at will by anyone who feels the particular need.

Anyway, I'm going to do some thinking of this, figuring out a way to plan the system so that it scales to my needs. Which I know I could have done with this blog with tagging in the meta data but it always seemed like an aside. It's something to do later, instead of Bookstack which requires the structure up front. So I'm going to try a migration. Probably.

And if I don't post again... I guess you know why.