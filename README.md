# What / Why
A fork of gnome-clocks patched to my liking

---

# Setup
## Deps
sudo pacman -S --needed base-devel meson ninja vala vorbis-tools itstool

## Setup Build (One-time)
meson setup build --prefix=/usr/local -Dprofile=development

## Build
pkill -x gnome-clocks
meson compile -C build
meson devenv -C build ./src/gnome-clocks

## Replace gnome-clocks
meson configure build -Dprofile=default
meson compile -C build
sudo pacman -R gnome-clocks
sudo meson install -C build

---

## Compliance with license
Files modified can be seen in the git commit history
Link to where source: https://github.com/GNOME/gnome-calendar
