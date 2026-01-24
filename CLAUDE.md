# Waybar Personal Build

Personal fork of [Alexays/Waybar](https://github.com/Alexays/Waybar) with niri taskbar features.

## Repository Status

- **origin**: `https://github.com/rucnyz/Waybar.git` (personal fork)
- **upstream**: `https://github.com/Alexays/Waybar` (official upstream)
- **main branch**: `feat/niri-taskbar-only` - adds niri workspaces taskbar-only mode and stacked window CSS class

## Sync with Upstream

```bash
git fetch upstream
git checkout master
git merge upstream/master
git push origin master

# Update feature branch
git checkout feat/niri-taskbar-only
git rebase master
git push --force-with-lease origin feat/niri-taskbar-only
```

## Build & Install

```bash
# First time setup (install to ~/.local)
meson setup build --prefix=$HOME/.local -Dsystemd=disabled

# Build
ninja -C build

# Install
ninja -C build install
```

Install location: `~/.local/bin/waybar`

## Configuration

- Install prefix: `~/.local`
- systemd service: disabled (waybar is started via niri config, systemd not needed)

## Dependencies (Arch Linux)

```bash
pacman -S --asdeps gtkmm3 jsoncpp libsigc++ fmt wayland chrono-date spdlog \
  gtk3 gobject-introspection libgirepository libpulse libnl \
  libappindicator-gtk3 libdbusmenu-gtk3 libmpdclient sndio libevdev \
  libxkbcommon upower meson cmake scdoc wayland-protocols glib2-devel
```
