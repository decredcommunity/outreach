# Decred Journal Production Guidelines

## Style, Editing

### Use canonical links without tracking

1. Remove any tracking parameters like Medium's `gi=...`, Google Analytics `utm_...`, etc. As a general rule, remove any URL parameters that don't break the link.

2. Ensure URLs are [canonical](https://en.wikipedia.org/wiki/Canonical_link_element). This implies using www.reddit.com over old.reddit.com. On most pages canonical link can be found in `<link rel="canonical" href="..."/>` in the page source. Use of canonical links improves linking of content together (e.g. on Reddit).

**Examples**

Non-canonical URLs with junk parameters:

https://www.youtube.com/watch?v=3RGoUQK0g24&feature=share

https://youtu.be/3RGoUQK0g24

Canonical URL: https://www.youtube.com/watch?v=3RGoUQK0g24

Forbes tracking (remove the `#425f36a11067`):

https://www.forbes.com/sites/kenrapoza/2019/06/20/facebooks-libra-coin-is-both-vampire-project-and-regulatory-nightmare/#425f36a11067

Medium tracking (remove the `?gi=68a95d076f04`):

https://hackernoon.com/decred-wants-you-be-one-of-the-first-to-test-the-dcr-lightning-network-dd9ecf14d95e?gi=68a95d076f04

### Markdown

Use backslash `\` to escape underscore `_` so it won't be treated as italics. Example: `under\_score`.

Avoid Markdown features that are problematic in the Medium version:

* Paragraphs and blockquotes inside list items
* Nested lists

See this excellent [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) of Markdown features.
