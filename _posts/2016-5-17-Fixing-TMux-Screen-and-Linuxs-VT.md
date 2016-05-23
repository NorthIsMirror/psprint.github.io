---
layout: post
title: Fixing TMux, Screen and Linux's VT
---

If `TERM=screen-256color` (often the case for `tmux` and `screen` sessions) then
`ncv` terminfo capability will have `2`nd bit set. This in general means that
underlining text won't work. To fix this by creating your own `ncv=0`-equipped
terminfo file, run:

```zsh
{ infocmp -x screen-256color; printf '\t%s\n' 'ncv@,'; } > /tmp/t && tic -x /tmp/t
```

A file will be created in directory `~/.terminfo` and will be automatically
used, `tmux` and `screen` will work. Similar is for Linux virtual terminal:

```zsh
{ infocmp -x linux; printf '\t%s\n' 'ncv@,'; } > /tmp/t && tic -x /tmp/t
```

It will not display underline properly, but will instead highlight by a color,
which is quite nice. The same will not work for FreeBSD's VT. `Zsh Navigation
Tools` and other projects will detect if that VT is used and will revert to
highlighting elements via `reverse` mode.

