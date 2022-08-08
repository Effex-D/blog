---
title: "Replacing OpenVPN with Nord Meshnet"
date: 2022-08-06
author: Effex
tags: []
---

VPNs have always been somewhat annoying for me to configure. Like a lot of people running a homelab, I use a forward facing node with a VPN attached to route traffic through to my internal servers. This requires me to do one of two things:

1) Set up a VPN Server on my forward facing server. This increases my attack surface, as it requires an additional port open on my server as opposed to HTTPS and restricted, ip-allowlisted SSH.
2) I can set up a VPN server on my personal network router. I don't like this as I prefer to restrict all connection towards my internal network.

In the past, I've gone with option 1. And it worked reasonably well. But the setup was always a pain in the ass. It involved setting up a listening daemon on the server and a bunch of clients for each device connecting. Once it was up and running, it went just fine. But it took a couple of hours of teasing and tweaking. For each client, I was generating new certificates and a new set of client configs for every machine, even if I was only connecting to it for a few minutes. 

![Architecture 0](/blog/assets/images/arch0.png)

Then NordVPN, who are my preferred VPN provider despite Reddit's flaccid anger over it, came out with a new feature. Meshnet. A simple tool for generating private, point-to-point private networks with minimal configuration.

It sets up with two commands and is fully functional in minutes. 

```
nordvpn login
nordvpn set meshnet on
```

While it's not great for production workloads, it comes with a NordVPN subscription, so for those of us who maintain one, it is absolutely free. Here is the architecture with Meshnet:

![Architecture 1](/blog/assets/images/arch1.png)

It does have limitations, such as only 6 machines being actively connected at once. But at least for my home lab purposes, that's worked pretty well. And if that covers enough hosts for you, it might work pretty well for you too.