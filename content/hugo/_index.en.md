---
title: "Host Your Hugo Website"
date: 2018-12-29T11:02:05+06:00
img: "/hugo-logo-wide.svg"
weight: 1
description: "Find out how to get a Hugo website up and running on MarkdownSite quickly."
type : "docs"
---

[Hugo](https://gohugo.io/) is a popular static website generator.

MarkdownSite fully supports websites made with Hugo.

Make sure that your website is fully built with `hugo -D` in the root of the git repository.

This will ensure that the `public/` directory has all of the files required to serve the website.

Commit your repository to your git provider and then go to [MarkdownSite.com](https://markdownsite.com/) and enter the git URL that is used to clone the repository.

Click **Build My Site** and you will be brought to the status page for your MarkdownSite and it will be rebuilding.

If you use an **ssh** clone URL, MarkdownSite may need to be given access to your repository.  You can find [the public key here](https://markdownsite.com/sshkey.txt).

