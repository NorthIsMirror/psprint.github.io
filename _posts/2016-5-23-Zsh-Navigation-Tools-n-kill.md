---
layout: post
title: Zsh Navigation Tools – n-kill
---

One of main components of
[Zsh Navigation Tools](https://github.com/psprint/zsh-navigation-tools) is
`n-kill`. It allows to quickly gain orientation in process list and send signal
to selected process. First, it does case-insensitive completion on **words**
found in process list.

### Grepping and filtering

Such word is then used to grep process list. Instead of grepping, you may also
use filtering. Hitting `/` will start search mode (leave with `F3` or `ESC`) in
which multi-term search query might be enterred, such as `git commit`. What can
be found in result might be:

```sh
[PID]  vim /Users/sgniazdowski/github/ztrace/.git/COMMIT_EDITMSG
```

As you can see, "git" and "COMMIT" are separated by `/` but that's not a
problem for multi-term searching.

### Search keywords

Functionality that will quickly iterate over predefined search keywords. Press
`Ctrl-X`, `F2` or `Ctrl-/` to iterate across what's defined in
`~/.config/znt/n-kill.conf` in `keywords` option:

```zsh
# Search keywords, iterated with F2 or Ctrl-X or Ctrl-/
local -a keywords
keywords=( "vim" "git" "git commit" "firefox" "mplayer" )
```

This can be also configured via `zshrc`, by setting znt_kill_keywords (global)
array:

```zsh
znt_kill_keywords=( "git" "git commit" "vim" "firefox" "mplayer" )
```

### Video

View on [asciinema](https://asciinema.org/a/46457)

[![asciicast](https://asciinema.org/a/46457.png)](https://asciinema.org/a/46457)
