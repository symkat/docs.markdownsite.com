---
title: "Host Your Jekyll Website"
date: 2022-03-21T08:00:00+08:00
img: "/logo-jekyll.png"
weight: 1
description: "Find out how to get a Hugo website up and running on MarkdownSite quickly."
type : "docs"
---

[Jekyll](https://jekyllrb.com/) is a popular static website generator.

MarkdownSite supports websites made with Jekyll, with one tweak to the configuration file.

Make sure that your website is fully built with `jekyll build` in the root of the git repository.

This will ensure that the `_site/` directory has all of the files required to serve the website.

Create a file named `.markdownsite.yml` in the root of the git repository and add the following content.

```
webroot: _site
```

This will ensure that MarkdownSite uses the content from `_site` to serve your website.

Commit your repository to your git provider and then go to [MarkdownSite.com](https://markdownsite.com/) and enter the git URL that is used to clone the repository.

Click **Build My Site** and you will be brought to the status page for your MarkdownSite and it will be rebuilding.

If you use an **ssh** clone URL, MarkdownSite may need to be given access to your repository.  You can find [the public key here](https://markdownsite.com/sshkey.txt).

