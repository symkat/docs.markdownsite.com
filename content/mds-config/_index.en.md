---
title: "YAML Config"
date: 2022-03-21T08:00:00+08:00
icon: "ti-settings"
weight: 4
description: "Like most things, MarkdownSite can be customized with the use of a special YAML file.  Learn about all of the configuration options here."
type : "docs"
---

MarkdownSite can be configured with a `.markdownsite.yml` file in the root of the domain.

| Key     | What it does                             | Default    |
| ------- | ---------------------------------------- | ---------- |
| webroot | Change the directory for static files.   | public/    |
| site    | Change the directory for markdown files. | site/      | 
| branch  | Change the branch to build the site from | master     | 
| domain  | Set the domain to use                    | \***none** |

#### Webroot

The default webroot is `public/`.  Files in that directory will be available from your website.

Adding this key will change the directory that is used for static files to include in your website.

#### Site

The default directory to scan for markdown files is `site/`.  Files in that directory will be converted to HTML and served to the website requesters.

Adding this key will change the directory that is used for finding markdown files to include in your website.

#### Branch

If a specific branch should be checked out after the `git clone`, use this key to specify the branch.

#### Domain

To change the domain to a custom domain, use this key.  Note that using this key without having the feature enabled will result in the build failing.

<hr />

A configuration file that brings some of these features together might look like this:

```
---
webroot: static
site:    pages
domain: myproject.markdownsite.net
```
