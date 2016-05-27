---
layout: post
title: Zsh Navigation Tools – approximate matching
---

[Zsh Navigation Tools](https://github.com/psprint/zsh-navigation-tools)
support approximate matching – pressing `Ctrl-F` during search will
allow 1 or 2 errors in what is typed in. This is near fuzzy matching,
but is aimed at typos.

The feature uses original Zsh capabilities, the same that allow e.g.
autocorrection to work. Main difference between the feature and fuzzy
matching is that entries are still sorted in order found in e.g.
history, not according to similarity between what is entered and found.

View on [asciinema](https://asciinema.org/a/47089)

<script type="text/javascript" src="https://asciinema.org/a/47089.js" id="asciicast-47089" async></script>
