---
author: bee
published_utc: 2022-12-23
---

# Platforms

Tips for publishing on various platforms.


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


### Markdown

- Escape any underscore `_` or asterisk `*` that you do not use for styling (to make text italic or bold). Put backslash `\` before underscore/asterisk to "escape" it. This prevents undesired italic/bold styling. Example: `under\_score`.
- See this excellent [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) of Markdown features.
- Learn about Markdown limitations and bugs of each platform you use.

**GitHub Pages specifics**

1\. Avoid the pipe `|` character, it may trigger GitHub Pages to render an unwanted table. This does not happen on regular GitHub and can easily go unnoticed.

**Anything outside GitHub**

1\. Fix local links manually.

A link like `[other doc](other-doc.md)` works on GitHub and GitHub Pages but other platforms have no way of knowing where such link should point to. Best case is it will be converted to an absolute `github.io` link (if copy-pasting rich text from `github.io`), worst case is it becomes a dead link.

Therefore, each local link must be manually replaced with a proper link to the relevant document hosted on that platform.
