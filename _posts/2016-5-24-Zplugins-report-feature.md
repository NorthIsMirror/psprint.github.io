---
layout: post
title: Zplugin's report feature
---

One of main [Zplugin's](https://github.com/psprint/zplugin) fatures is
reporting. It's possible to quickly recognize what plugin does,
provides, how to use it. Let's see plugin `willghatch/zsh-snippets` as
an example. It's report (obtained via `zplugin report
willghatch/zsh-snippets`) is:

```
Plugin report for willghatch/zsh-snippets
-----------------------------------------
Source snippets.plugin.zsh
Zle -N snippet-expand
Bindkey ^[x snippet-expand
Zle -N run-help-list-snippets

Functions created:
help-list-snippets run-help-list-snippets
snippet-add        snippet-expand

Variables added or redefined:
snippets  [ "" -> association ]
```

What do we get? We see that a key combination `Meta-x` (or `Alt-x`, `Esc
x`) is bound. That is apparently the main way the plugin should be used
(confirmed – that's true). Also, we see a widget
`run-help-list-snippets` that isn't bound. So we can probably bind it.
Four functions are created, and one of them starts with 'help-'
– confirmed that this function will provide information on snippets.
Function `snippet-add` looks like a way to add own snippet (confirmed).
Next are some implementation details – snippets are apparently kept in
`snippets` hash and expanded via `snippet-expand` function.

As we can see, reports allow us to recognize code we are introducing to
our system. `Zplugin` has more ways of doing that – commands: `recently`,
`changes`, `glance`, `stress`.
