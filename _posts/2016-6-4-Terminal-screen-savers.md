---
layout: post
title: Terminal screen savers
---

[zsh-morpho](https://github.com/psprint/zsh-morpho) is a plugin that
will run screen saver in terminal window after some time. It will
be the last terminal in which a commad has been run. Provided are
four screen savers: `zmorpho`, `zmandelbrot`, `zblank`, `pmorpho`.

`zmorpho` is the default screen saver. It implements morphogenesis
algorithm to produce random, beautiful images. Examples:

![zsh-morpho image]({{ site.baseurl }}/images/island.png)

![zsh-morpho image]({{ site.baseurl }}/images/heart.png)

![zsh-morpho image]({{ site.baseurl }}/images/pantofelek.png)

`pmorpho` is the same algorithm but implemented in python (runs faster).
`zmandelbrot` implements drawing Mandelbrot fractal. `zblank` just
blanks the terminal screen.

### Configuration

`zsh-morpho` can be configured via following zstyles:

```zsh
zstyle ":morpho" screen-saver "zmorpho" # select screen saver "zmorpho"; available: zmorpho, zmandelbrot, zblank, pmorpho
                                        # this  can also be a command, e.g. "cmatrix"
zstyle ":morpho" arguments "-s"         # arguments given to screen saver program; -s - every key press ends
zstyle ":morpho" delay "290"            # 5 minutes before screen saver starts
zstyle ":morpho" check-interval "60"    # check every 1 minute if to run screen saver
```

### Installation

This is a standalone plugin which means that it can be just sourced:

```zsh
source {where-zsh-morpho-is}/zsh-morpho.plugin.zsh
```

A plugin manager can also be used. For example, with
[Zplugin](https://github.com/psprint/zplugin), one has to
add `zplugin load psprint zsh-morpho` to `~/.zshrc`
