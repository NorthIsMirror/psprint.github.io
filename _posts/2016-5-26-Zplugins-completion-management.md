---
layout: post
title: Zplugin's completion management
---

[Zplugin's](https://github.com/psprint/zplugin) has advanced completion
management features. Basically, when you first load a plugin, it has all
its completions (i.e. files starting with "`_`") simlinked to
`~/.zplugin/completions`. Only this single directory is added to
`$FPATH` (and thus, you can call `compinit` immedietaly after sourcing
`Zplugin`).

Next, you can manage the completions. Command `clist` will show them and
mark if a completion is disabled:

```
# zplg clist
cd-gitroot  mollifier/cd-gitroot
n-kill      psprint/zsh-navigation-tools
parallels   benclark/parallels-zsh-plugin
zplugin     _local/zplugin
favrm       or17191/going_places [disabled]
go          or17191/going_places [disabled]
```

You can enable or disable a completion via `cenable` and `cdisable`
commands. To find all completions provided by plugins, installed or not,
issue `csearch` command:

```
# zplg csearch
[+] is installed, [-] uninstalled, [+-] partially installed
[+] _local/zplugin                      _zplugin
[+] benclark/parallels-zsh-plugin       _parallels
[-] fuzzylogiq/autopkg-zsh-completion   _autopkg
[+] mollifier/cd-gitroot                _cd-gitroot
[+] or17191/going_places                _favrm, _go
[+] psprint/zsh-cmd-architect           _xauth
[-] psprint/zsh-editing-workbench       _cp
[+] psprint/zsh-navigation-tools        _n-kill
[-] tevren/gitfast-zsh-plugin           _git
```

Let's install a completion with `creinstall` command (this is normally
done when first loading a plugin):

```
# zplg creinstall fuzzylogiq/autopkg-zsh-completion
Symlinking completion `_autopkg' to
/Users/sgniazdowski/.zplugin/completions
Forgetting completion `_autopkg'...

Initializing completion (compinit)...
```

To uninstall, use `cuninstall` command:

```
# zplg cuninstall fuzzylogiq/autopkg-zsh-completion
Uninstalling completion `_autopkg'
Forgetting commands completed by `_autopkg':
Unsetting autopkg
Forgetting completion `_autopkg'...

Uninstalled 1 completions
Initializing completion (compinit)...
```

All this brings order to system – only single entry in `$FPATH`, ability
to quickly recognize what's provided and disable it if needed. Typical
plugin managers will add each plugin's directory to `$FPATH`. Having
loaded 10 plugins, there would be 10 additional entries in it. And no
control over what's active.
