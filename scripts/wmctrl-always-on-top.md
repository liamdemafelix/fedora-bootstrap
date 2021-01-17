# Always on Top shortcut

1. Create a new Keyboard Shortcut via Gnome Settings.
2. For the command, use:

```
bash -c 'wmctrl -r :ACTIVE: -b $([[ $(xprop -id $(xprop -root -f _NET_ACTIVE_WINDOW 0x " \$0\\n" _NET_ACTIVE_WINDOW | awk "{print \$2}") _NET_WM_STATE) =~ "ABOVE" ]] && echo "remove" || echo "add"),above'
```

3. Specify the shortcut key (I use `CTRL` + `Space`).
