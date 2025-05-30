# dwm - dynamic window manager

dwm is minimal wm for nerds.

## Quick start

dwm depends on libX11, libXinerama and libXft.
Also this config depends on `maim` for taking screenshots.

```shell
# on fedora
sudo dnf install libX11-devel libXinerama-devel libXft-devel maim
sudo make clean install
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
- `Alt-q` for killing window (`Alt-Shift-c` by default)

#### Running programs

- `Alt-Return` for opening `st` terminal (`Alt-Shift-Return` by default)
- `Alt-b` for opening `qutebrowser`
- `Alt-e` for opening `telegram-desktop`

#### Media

- `Vol+/-` media keys for adjusting sound
- `Alt-a` for changing default audio output (custom script that works only on my machine. dwm trying to execute it at `~/.config/toggle_sink.sh` path)

---

### Colorscheme

Subsituted cyan color with one of the default gray colors to achieve dark colorscheme.
Also changed title bg color to bar color with titlecolor patch.

---

### Source code

Included X11/XF86keysym.h in dwm.c for media keys (for example vol+/-) to be working.

Changed monocle mode rendering for adding gaps (fullgaps patch adds gaps only in tile mode).
