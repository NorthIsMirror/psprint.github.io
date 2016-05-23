---
layout: post
title: 256 color themes in Zsh Navigation Tools
---

Zsh Navigation Tools support color themes that can be tried out by
pressing `Ctrl-T` (next theme) and `Ctrl-G` (previous theme). They
are configured via `themes` variable in `~/.config/znt/n-list.conf`:

```zsh
# Combinations of colors to try out with Ctrl-T and Ctrl-G
# The last number is the bold option, 0 or 1
local -a themes
themes=( "white/black/0" "white/black/1" "green/black/0"
         "green/black/1" "white/blue/0" "white/blue/1"
         "magenta/black/0" "magenta/black/1" )
```

Other way to configure is utilizing `ZNT`'s integration with `zshrc` and
setting variable `znt_list_themes` there:

```zsh
znt_list_themes=( "green/black/1" "black/white/1" )
```

### Video

View on [asciinema](https://asciinema.org/a/46477)

<script type="text/javascript" src="https://asciinema.org/a/46477.js" id="asciicast-46477" async></script>
