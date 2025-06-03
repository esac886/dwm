# dwm - dynamic window manager

dwm is minimal wm for nerds.

## Quick start

dwm depends on libX11, libXinerama and libXft.

Also this config depends on:
- maim for screenshots
- Cascadia Mono NF by default (you can change font in `config.h`).
- my [record script](https://github.com/esac886/scripts/blob/main/record) for recording screen with audio (it uses ffmpeg, slop and pactl for working with pipewire)
- my [toggle script](https://github.com/esac886/scripts/blob/main/toggle-sink) for toggling default output audio device for pipewire. it'll work only on my machine due to hardcoded audio sinks

```shell
# on fedora
sudo dnf install libX11-devel libXinerama-devel libXft-devel maim cascadia-mono-nerd-fonts
sudo make clean install
# to use record and toggling audio output keybindings you must install scripts and put them in $PATH
```

## Patches applied

- [pertag](https://dwm.suckless.org/patches/pertag)
- [fullgaps](https://dwm.suckless.org/patches/fullgaps)
- [titlecolor](https://dwm.suckless.org/patches/titlecolor)
- [hide_vacant_tags](https://dwm.suckless.org/patches/hide_vacant_tags)
- [noborder](https://dwm.suckless.org/patches/noborder)
- [refreshrate](https://dwm.suckless.org/patches/refreshrate)

## My additions

### Keymaps

#### WM

- `Alt-s` for swapping windows in tile layout mode (`Alt-Return` by default)
- `Alt-Shift-f` for toggling floating on window (`Alt-Shift-Space` by default)
- `Alt-Shift-b` for toggling bar (`Alt-b` by default)
- `Alt-g` for toggling gaps
- `Alt-q` for killing window (`Alt-Shift-c` by default)

#### Running programs

- `Alt-Return` for opening `st` terminal (`Alt-Shift-Return` by default)
- `Alt-b` for opening `qutebrowser`
- `Alt-e` for opening `telegram-desktop`
- `Alt-r` executes `record -il` from $PATH (records screen with default loopback sound)
- `Alt-Shift-r` executes `record -i` from $PATH (records screen without sound)
- `Alt-Ctrl-r` executes `record -is` from $PATH (records selected region of screen without sound)

#### Media

- `Vol+/-` media keys for adjusting sound (it uses wireplumber by default)
- `Alt-a` executes `toggle-sink` from $PATH (custom script that works only on my machine. [see](https://github.com/esac886/scripts/blob/main/toggle-sink)) 

---

### Colorscheme

Subsituted cyan color with one of the default gray colors to achieve dark colorscheme.
Also changed title bg color to bar color with titlecolor patch.

---

### Source code

Included X11/XF86keysym.h in dwm.c for media keys (for example vol+/-) to be working.

Changed monocle mode rendering for adding gaps (fullgaps patch adds gaps only in tile mode).
