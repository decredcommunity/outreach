---
author: bee
published_utc: 2022-12-23
---

# Platforms

Tips for publishing on various platforms.

On this page:

- [Any platform](#any-platform)
- [Markdown common](#markdown)
- [GitHub Pages](#github-pages)

Major platforms have their own pages:

- [Ghost](ghost.md)
- [Instagram](instagram.md)
- [Medium](medium.md)
- [Odysee](odysee.md)
- [Twitter](twitter.md)


## Any platform


### Use canonical links without tracking

First, remove any tracking parameters like Medium's `gi=...`, Google Analytics `utm_...`, etc. As a general rule, remove any URL parameters that don't break the link. "URL parameters" is the stuff that comes after `?` in the URL.

Second, ensure URLs are [canonical](https://en.wikipedia.org/wiki/Canonical_link_element). This means using `www.reddit.com` over `old.reddit.com`, `www.youtube.com` over `youtu.be`, and so on. On most pages canonical link can be found in `<link rel="canonical" href="..."/>` in the page source. Use of canonical links improves linking of content together (e.g. on Reddit).

**Examples**

Bad: junk parameters: https://www.youtube.com/watch?v=3RGoUQK0g24&feature=share

Bad: non canonical domain: https://youtu.be/3RGoUQK0g24

Good: https://www.youtube.com/watch?v=3RGoUQK0g24

Bad: Forbes tracking (remove the `#425f36a11067`):

https://www.forbes.com/sites/kenrapoza/2019/06/20/facebooks-libra-coin-is-both-vampire-project-and-regulatory-nightmare/#425f36a11067

Bad: Medium tracking (remove the `?gi=68a95d076f04`):

https://hackernoon.com/decred-wants-you-be-one-of-the-first-to-test-the-dcr-lightning-network-dd9ecf14d95e?gi=68a95d076f04

**Exceptions**

Short non-canonical links like `youtu.be` or `t.co` are okay if you need to fit into a small character limit, like on [Twitter](twitter.md) or [Instagram](instagram.md).


### Wipe image metadata

Image files may store a ton of hidden metadata, like what camera made a photo with what settings, or what software was used to create the image. There are stories of proprietary software silently inserting user's license number into the image.

To avoid any unexpected behavior from image editing software, re-save the image with a tool that is known to remove metadata.


### Markdown

Markdown is a popular format for adding simple styles and links to plain text. Reasons to learn and use Markdown in your content:

- It is relatively easy to learn.
- Create lists, links, and add styles as you type, without switching to mouse to hunt that toolbar button.
- Markdown documents can be published on many platforms, including Ghost, Odysee, GitHub Pages. These platforms render Markdown as pretty HTML documents with clickable links, images, tables, and more.
- Being a *text* format, Markdown documents fit nicely in version control systems like Git. Document's past versions can be easily compared to see who edited what and when. This is much harder to achieve in *binary* formats like DOCX or PDF.

Bookmark the [Markdown Guide](https://www.markdownguide.org/basic-syntax/) or the excellent [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) for quick access until it becomes part of your muscle memory.

Recommendations below are valid for all platforms. On top of that, learn about Markdown limitations and bugs of [each platform you use](#platforms).

**Avoid unwanted styling**

Escape any underscore `_` or asterisk `*` that you do not use for styling (to make text italic or bold). Put backslash `\` before underscore orasterisk to "escape" it. This prevents undesired italic/bold styling.

Example: `under\_score`.

**Fix local links**

A link like `[other doc](other-doc.md)` works on GitHub and GitHub Pages but other platforms have no way of knowing where such link should point to. Best case is it will be converted to an absolute `github.io` link (if copy-pasting rich text from `github.io` page), worst case is it becomes a dead link.

Therefore, each local link must be manually replaced with a proper link to the relevant document hosted on that platform.


## GitHub Pages

Image size:

- If you target slow network connections like [Decred Journal](https://xaur.github.io/decred-news/) does, stick to small images around 768x384 px (2:1) and under 100 KB.


### Markdown

Gotchas:

1\. Avoid the pipe `|` character, it may trigger GitHub Pages to render an unwanted table. This does not happen on regular GitHub and can easily go unnoticed.

#### Links to subheadings

- GitHub Pages automatically generates HTML anchors from Markdown headings. Anchors can be used in links that jump to specific sections of the document. This is useful for table of contents.
- Anchors are created for each Markdown heading (levels from 1 to 6).
- Example: Markdown heading `## DCRDEX v0.5.7 Release` results in an HTML anchor `#dcrdex-v057-release`.
- The algorithm of deriving an anchor from the heading is roughly:
  - Convert all letters to lowercase.
  - Replace all spaces with a hyphen `-`.
  - Remove periods `.` and some other punctuation.
- To use the anchor in your link, just append it at the end.
  - Local link example: `see the [development](#development) section`.
  - Full link example: `https://xaur.github.io/decred-news/journal/202211#development`
- You can create additional invisible anchors by injecting HTML like `<a id="my-custom-anchor"/>` _before_ the text you want to jump to.
- Anchors work without JavaScript (unlike normal GitHub).
