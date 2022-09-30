---
title: "Interesting web traffic"
date: 2022-09-30
author: Effex
tags: ["infosec"]
---

I got bored and decided to have a quick browse of my web server's access logs.

#### Directory Traversal

```
GET /remote/fgt_lang?lang=/../../../..//////////dev/cmdb/sslvpn_websession HTTP/1.1
```
This one is a web traversal attack attempt. From what I can see it is intended for Fortios SSL VPNs. Which my server does not run. More info:

https://gist.github.com/code-machina/bae5555a771062f2a8225fd4731ae3f7

#### Directory Traversal 2

Then we have another directory traversal attack:

```
/cgi-bin/.%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/etc/hosts HTTP/1.1
```

This one is directed at Apache. Which my server does not run. Details:

https://blogs.juniper.net/en-us/threat-research/apache-http-server-cve-2021-42013-and-cve-2021-41773-exploited

#### A Scanner Darkly

The larger log entry seems to be part of zgrab, a tool for fast scanning web infrastructure.

```
\x05\x01\xF4GY\xB3\xBF\x169\x88\xD0\x92$\xD5<\x89

144.126.214.96 - - [30/Sep/2022:01:50:29 +0000] "\x05\x01\xF4GY\xB3\xBF\x169\x88\xD0\x92$\xD5<\x89" 400 157 "-" "-"
144.126.214.96 - - [30/Sep/2022:01:50:30 +0000] "GET /ab2g HTTP/1.1" 404 125 "-" "Mozilla/5.0 zgrab/0.x"
144.126.214.96 - - [30/Sep/2022:01:50:31 +0000] "GET /ab2h HTTP/1.1" 404 125 "-" "Mozilla/5.0 zgrab/0.x"
144.126.214.96 - - [30/Sep/2022:01:50:35 +0000] "GET / HTTP/1.1" 200 725 "-" "Mozilla/5.0 zgrab/0.x"
144.126.214.96 - - [30/Sep/2022:01:50:35 +0000] "GET / HTTP/1.1" 400 255 "-" "Mozilla/5.0 zgrab/0.x"
```

#### More Directory Traversal

Another interesting set of attack attempts. Some obfuscated directory traversal again, this time targetting PHP, which has never been on my box.

```
161.35.188.242 - - [30/Sep/2022:00:26:30 +0000] "GET / HTTP/1.1" 400 157 "-" "-"
161.35.188.242 - - [30/Sep/2022:00:26:58 +0000] "GET / HTTP/1.1" 200 1329 "-" "l9tcpid/v1.1.0"
161.35.188.242 - - [30/Sep/2022:00:27:00 +0000] "PUT /vendor/phpunit/phpunit/src/Util/PHP/eval-stdin.php HTTP/1.1" 404 125 "-" "Go-http-client/1.1"
161.35.188.242 - - [30/Sep/2022:00:27:02 +0000] "GET /cgi-bin/.%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/etc/hosts HTTP/1.1" 400 157 "-" "-"
161.35.188.242 - - [30/Sep/2022:00:27:02 +0000] "GET /cgi-bin/.%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/%2e%2e/etc/hosts HTTP/1.1" 400 157 "-" "-"
161.35.188.242 - - [30/Sep/2022:00:27:03 +0000] "GET /.DS_Store HTTP/1.1" 404 125 "-" "Go-http-client/1.1"
```

https://www.cvedetails.com/cve/CVE-2017-9841/

#### What any of this means?

All of these attacks are shots in the dark, random attacks shot at a random system (or likely hundreds, thousands, a hundred-thousand random systems) with the hope that something might stick.

We've exited the age of reconnaissance, and entered the age of high volume, the age of randomly (or methodologically) targetted attacks.

It has become more effective to start by throwing the kitchen sink.
