---
layout: post
title:  "Interpreting Ignorance"
date:   2020-04-09 14:34:46 +0000
author: Effex
---

The second thing I want to discuss (if you haven't read the first blog post, go here) is the actual implementation of reverse proxies to support HTTPS in non HTTP systems. I am using OCM/Compendium as the example, but this applies everywhere that standard HTTP is provided.

About a year ago now I was dragged into a discussion between a client's marketing department and their tech department. The tech department refused to allow this reverse proxy setup for HTTPS upgrade for OCM.

The thing is, their reasons were all valid. They argued that a Man-in-the Middle attack was possible between the HTTP non-encrypted source and the reverse proxy, which would give legitimacy (and encryption) to any illicit material that was inserted downstream. Not to mention the ability to intercept, log and change any form requests that passed through the un-encrypted space.

They were absolutely right. It is possible.

But that's the thing about possible. It doesn't mean likely. It just means that is it not impossible.

This is the argument of "Security by Restriction" vs "Security as an Enabler". Should InfoSec be allowed to stand in the way because something was not bulletproof?

In IT, even bulletproof systems do not stay bulletproof forever. The deluge of security patches and updates that are pushed upon us daily are a testament to that.

The client had some excellent suggestions. They recommended that the machine be put on the same network as the unencrypted service. Except we don't own the service, so we have no control over that.

They suggested a VPN. Except the service doesn't support that.

They suggested an encrypted tunnel. But the service didn't support it.

So they said we could not proceed with the project.

It was the correct call, from information security standards. They'd followed the protocol. We could not comply with their suggestions. But they overlooked one small matter.

The site was, and still is, now hosted with plain HTTP. No encryption. Anywhere.

IT security flexed the part over which they had control, ignoring the parts they did not.

This is the equivalent of saying to a medieval soldier "We have a suit of armor in your size, but it is missing a helmet and the left glove. It does not offer full protection. As such, we are sending you into battle naked."

To be perfectly clear, the kind of attacks they were talking about, server-to-server man-in-the-middle attacks, are very rare. They require large resources, and the ability to trick large portions of the backbone networks that support the internet. I cannot find a single documented case of this happening on a large scale.

However, server-to-browser man-in-the-middle attacks are very common. It is much easier to trick a small network to pass you data than it is to trick a section of the internet backbone. I perform server-to-browser man-in-the-middle attacks almost weekly, whenever I grow bored and my wife is looking at one of those news sites that still don't force TLS as standard. She's got used to seeing my face along-side a news headline of "Dangerous Criminal escaped. Wanted for flashing. ROMs."

This was security policy implemented in a vacuum, with no regard for business sense or even general common sense. The old ideal, security by restriction, the standpoint of "you do not meet my requirements, so you cannot do this" is dead.

Instead, security should take the standpoint of "How do we mitigate as much of the risk as possible, and does that leave an acceptable, functional system for all parties?"

Security as an enabler.

Simple.
