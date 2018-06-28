---
title: "Beamer-specific extensions"
section-titles: false
toc-per-section: true
fontsize: 11pt
classoption:
- xcolor=table
- c
- slidestop
author:
- ArTeCS group
---

## Special beamer blocks

<div class="alertblock" title="This is the title of an alertblock">
And this is the **content** of the alertblock.
</div>

<div class="exampleblock" title="This is the title of an exampleblock">
And this is the **content** of the exampleblock.
</div>

<div class="consoleblock" title="This is the title of a consoleblock">
```
ls -lta # Or any other code, for example.
```
</div>

[And here, another way of creating an alert block.]{class="alertblock" title="Alertblock"}

## Transitions

[...First item (shown in all slides)...]{only="1-"}

[...Second item (only in second)...]{only="2"}

[...Third item (only in third)...]{only="3"}

