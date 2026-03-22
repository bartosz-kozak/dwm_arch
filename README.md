# dwm - my personal fork

> **Work in progress** — this is my custom build of dwm, actively being modified.

This is a personal fork of [dwm](https://dwm.suckless.org/) (dynamic window manager) by [suckless.org](https://suckless.org/). The original project is a minimal, fast, and hackable window manager for X written in C.

---

## My customizations

Changes from the upstream default config:

- **Modifier key**: changed from `Alt` (`Mod1Mask`) to `Super/Win` (`Mod4Mask`)
- **Font**: changed to `MesloLGS NF` (Nerd Font) for icon/glyph support in the status bar
- **Browser shortcuts**:
  - `Super + w` — launch qutebrowser
  - `Super + c` — launch Chromium

---

## Requirements

- Xlib header files
- `MesloLGS NF` (or another Nerd Font) installed on your system
- `st` (simple terminal) — default terminal emulator
- `dmenu` — application launcher
- `qutebrowser` and/or `chromium` if you want the browser shortcuts to work

---

## Installation

Edit `config.mk` to match your local setup, then:

```sh
make clean install
```

---

## Running dwm

Add to your `~/.xinitrc`:

```sh
exec dwm
```

For a status bar:

```sh
while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
do
    sleep 1
done &
exec dwm
```

---

## Key bindings (default + custom)

| Key | Action |
|-----|--------|
| `Super + p` | dmenu launcher |
| `Super + Shift + Return` | open terminal (st) |
| `Super + w` | open qutebrowser |
| `Super + c` | open Chromium |
| `Super + b` | toggle bar |
| `Super + j/k` | focus next/prev window |
| `Super + h/l` | resize master area |
| `Super + Return` | move window to master |
| `Super + t/f/m` | tile / float / monocle layout |
| `Super + Shift + c` | close window |
| `Super + Shift + q` | quit dwm |
| `Super + [1-9]` | switch to tag |

---

## Configuration

Edit `config.h` and recompile. dwm has no runtime config — all changes require a recompile:

```sh
make clean install
```

---

## License

Same as upstream dwm — MIT/X Consortium License. See `LICENSE` for details.

---

*Fork of [dwm 6.x](https://dwm.suckless.org/) — original authors: Anselm R Garbe and contributors.*
