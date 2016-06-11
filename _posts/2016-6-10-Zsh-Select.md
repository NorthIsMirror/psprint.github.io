---
layout: post
title: Zsh Select
---

I've written a tool that can substitute `fzf`, `selecta`, `sentaku` with and
thanks to out of the box Zsh features:

- patterns, allowing multi-term searching
- curses module
- approximate matching

All you need is a `Zsh` binary to be able to perform searching, selecting, and
approximately matching. This is really fun. Connecting existing functionalities
to obtain what other software packages need to carefully implement.

`Zsh-select` is robust, curses handles terminal very well, there are no calls
to external programs such as `sed`, and peformance is high – handled are 120
000 lines long inputs.

The file `zsh-select` can be copied to any bin directory. `Zsh` will serve as
say `Ruby`, and `zsh-select` will be a regular program available in system.

View on [asciinema](https://asciinema.org/a/48490). You can resize the video by pressing `Ctrl-+` or `Cmd-+`.

<script type="text/javascript" src="https://asciinema.org/a/48490.js" id="asciicast-48490" async></script>

