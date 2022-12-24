---
author: bee
published_utc: 2022-12-23
---

# Ghost

[Decred Magazine](https://www.decredmagazine.com/) runs on [Ghost](https://ghost.org/) so we need to know its gotchas.


## Markdown

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


## Other

4\. Add relevant tags. Your post will be shown on that tag's page.

5\. Featured image specifics

Logo and text overlay must not be too close to image border, or it may get cut off in some layouts.

6\. Add summary text.

It is shown under post title on various pages.
