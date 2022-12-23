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

**Ghost**

Decred Magazine runs on Ghost so we need to know its gotchas.

1\. Manually fix bullet lists with extra blanks between items.

Example. Ghost seems to render this:

```
- Item one.

- Item two.
```

Like this:

```
Item one.

Item two.
```

Blanks between items are useful to make each item more visible. In Ghost these need to be manually adjusted.

2\. Pay attention to multiline quote blocks.

These:

```
> Quoted paragraph 1.
> 
> Quoted paragraph 2.
```

May get rendered as two separate quote blocks instead of one connected block. Add right angle bracket followed by a space (`> `) to connect quoted paragraphs.

3\. Local links like `[other doc](other-doc.md)` must be fixed manually.

4\. Add relevant tags. Your post will be shown on that tag's page.

5\. Featured image specifics

Logo and text overlay must not be too close to image border, or it may get cut off in some layouts.

6\. Add summary text.

It is shown under post title on various pages.

**Medium specifics**

1\. Avoid complex Markdown that does not paste cleanly into Medium editor:

- Paragraph breaks and blockquotes inside list items. Keep list items simple.
- Nested lists.
- In general, avoid combining _any_ two structural features to be extra safe.
- Two adjacent blockquotes are merged in one if they are not separated by normal text. Try adding more blank lines to break them.

If you really want to use advanced Markdown features (e.g. on GitHub), prepare a separate, simplified Markdown file for Medium that work-arounds all Medium's formatting issues.

2\. Table of Contents must be recreated manually.

3\. Local links like `[other doc](other-doc.md)` must be fixed manually.

4\. Add relevant tags.

Some relevant Medium tags:

- https://medium.com/tag/decred
- https://medium.com/tag/cryptocurrency
- https://medium.com/tag/decentralized-exchange
- https://medium.com/tag/cryptocurrency-news
- https://medium.com/tag/crypto

5\. Fill the summary text.

It is 140 characters max and is shown under post title on listing pages like https://medium.com/decred or https://medium.com/decred/journals/home .

**Odysee specifics**

1\. Replace all "simple" usages of the `@` character with its HTML escape sequence `&#64;`.

  - "Simple" usages are the ones NOT inside link text (e.g. `[@HotUser](url...)`), NOT coming after a square bracket (e.g. `\[@HotUser, bla bla\]` - `@` is fine here), and NOT inside link URLs (e.g. `[bla bla](https://medium.com/@username/...)` - `@` is fine here).

  - Why: Odysee Markdown renderer tries to automatically create links on `@username`-s. Problems - it may tag or even notify an unintended person, and it adds ugly paragraph breaks.

2\. Convert local links to images to absolute links.

Example: `![](../img/202207.1.github.png)` -> `![](https://xaur.github.io/decred-news/img/202207.1.github.png)`.

3\. Convert local links to posts to absolute links.

Example: `[see June issue](202206.md)` -> `[see June issue](https://odysee.com/@Decred:c/decred-journal-2022-06:8)`.

4\. When publishing, pay attention to post ID. It cannot be changed later.

For example, DJ sticks to pattern `decred-journal-YYYY-MM`. Adjust for your post or post series.
