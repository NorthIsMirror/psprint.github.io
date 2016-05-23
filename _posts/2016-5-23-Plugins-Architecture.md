---
layout: post
title: Plugin's architecture
---

Zsh plugins may look scary, as they seem to have some sophisticated "architecture".
But in fact, plugins are really simple.

What a plugin actually is, is that:

1. It has its directory added to `fpath`
2. It has any first `*.plugin.zsh` file sourced (some plugin managers also follow
   to sourcing `*.init`, `*.zsh`, `*.sh`, etc. files)

That's it. When one contributes to Oh-My-Zsh or creates a plugin for any plugin manager, he only needs to account for this.
The same with doing any non-typical installation of `Zsh Navigation Tools` or other project from this site.
