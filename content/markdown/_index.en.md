---
title: "Native Markdown Support"
date: 2018-12-29T11:02:05+06:00
icon: "ti-smallcap"
weight: 3
description: "Learn about MDS's support for rendering markdown files."
type : "docs"
---

MarkdownSite supports rendering markdown files natively.

## File Mapping

By default markdown files are scanned for in `site/`.

This location can be overridden with the `site` key in the [YAML Config](/mds-config/).

When the website is live, requests will map like this table.

| HTTP Request  | File Paths Checked   |
| ------------- | -------------------- |
| /             | site/index.md        |
| /about        | site/about.md        |
| /about        | site/about/index.md  |
| /about.html   | site/about.md        |
| /about.htm    | site/about.md        |

If one of the files is not found, then there will be a 404 error.

## Rendering System

MarkdownSite uses [MarkdownSite::CGI](https://github.com/symkat/MarkdownSite/tree/master/CGI) to turn Markdown files into HTML files.

When a file is found, it is read with [Markdown::Compiler](https://github.com/symkat/Markdown-Compiler).  This creates `meta-data` from the header section, if available.  It turns the body of the markdown file into HTML.

The meta data and HTML is then given to an [EP Template](https://metacpan.org/dist/Mojolicious/view/lib/Mojolicious/Guides/Rendering.pod#Embedded-Perl) for rendering.  Once rendered, it is cached.

The header of the markdown file can declare various keys that impact what MarkdownSite::CGI does.

| System Key   | What It Does                          | Default Value |
| ------------ | ------------------------------------- | ------------- |
| theme        | Which theme to use                    | default       |
| template     | Which template from that theme to use | page          |

The default theme supports the following keys:

| Theme Key   | What It Does                           | Default Value |
| ------------ | ------------------------------------- | ------------- |
| title        | HTML title for page                   | none          |
| meta.author  | Value for meta field in header        | none          |
| meta.desc    | Value for meta field in header        | none          |


A markdown file that made use of these and has a custom template may look like the following:

```
---
title: Sonnet 121
meta.author: William Shakespeare
template: sonnet
---

’Tis better to be vile than vile esteemed
When not to be receives reproach of being,
And the just pleasure lost, which is so deemed
Not by our feeling but by others' seeing.
For why should others’ false adulterate eyes
Give salutation to my sportive blood?
Or on my frailties why are frailer spies,
Which in their wills count bad that I think good?
No, I am that I am; and they that level
At my abuses reckon up their own:
I may be straight though they themselves be bevel;
By their rank thoughts my deeds must not be shown,
    Unless this general evil they maintain:
    All men are bad and in their badness reign.
```

A markdown file can make use of none of these meta-data sections.

```
Hello **World**!

This is a perfectly fine file that is in
[markdown](https://en.wikipedia.org/wiki/Markdown).
```

