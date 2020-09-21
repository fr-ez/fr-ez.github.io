---
layout: post
title: HackTheBox - Learnaen
description: "Solution to the challenge Learnaen from HackTheBox"
category: hackthebox,ctf,challenge
---

Pretty easy challenge, nothing new here just vulnerable to bruteforcing.

I used `wfuzz`. I specified a postdata “password=FUZZ" where FUZZ is the word changed in each request. After trying with the quick and medium wordlists, I noticed that the length of the response when the password failed was 17 lines. I then specified a filter that only prints out the request that had more than 17 lines and ran it against the long list:

![Fuzzing 1]({{site.baseurl}}/images/posts/htb-learnaen/1.png)

Password: leonardo.

Verifying with Burp:

![Verification]({{site.baseurl}}/images/posts/htb-learnaen/2.png)

Flag: `HTB{l1k3_4_b0s5_s0n}`