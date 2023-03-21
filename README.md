# Hyprland version 0.23 on Arch linux

**Dr. Asifur Rahman Akonjee**

My youtube channel: https://www.youtube.com/@dr.asifakonjee

My github repo: https://www.github.com/asifakonjee

## CAUTION: Please READ the Hyprland wiki FIRST. Don't blindly copy/paste this repo.

## Requirements
1. Arch Linux Base Install
2. Paru

### Paru

Run as user NOT ROOT!

```
sudo pacman -S base-devel
git clone https://aur.archlinux.org/paru
cd paru
makepkg -si
```

### Packages

``` bash
sudo pacman -S gdb ninja gcc cmake libxcb xcb-proto xcb-util-keysyms libxfixes libx11 \
libxcomposite xorg-xinput libxrender pixman wayland-protocols cairo pango seatd \
libxkbcommon xcb-util-wm xorg-xwayland libinput libliftoff libdisplay-info


git clone --recursive https://github.com/hyprwm/Hyprland.git
cd Hyprland/
sudo make install

Paru -S git sddm-git waybar-hyprland alacritty-sixel-git foot libsixel rofi-lbonn-wayland-git thunar gvfs-mtp swayidle \
swaybg swaylock-effects-git wl-clipboard networkmanager-dmenu-git \
xfce-polkit dunst geany viewnior nwg-look xdg-desktop-portal-hyprland-git qt5-svg inetutils \
xdg-user-dirs pulsemixer pavucontrol qt5-graphicaleffects qt5-quickcontrols2 \
pipewire wireplumber grim slurp jq dunst qt5-wayland qt6-wayland qt5ct qt6ct kvantum kvantum-qt5-git kvantum-qt6-git
```
N.B.- Some points during installation. 
1. If you choose to install hyprland-git using paru choose rustup as dependency.
2. If it gives error, then install build from source according to offcial wiki guideline (Best way till now!).
3. During installation of xdg-desktop-portal-hyprland-git, choose xdg-desktop-portal-wlr, otherwise hyprland will not start. Make sure that you don't have other xdg-desktop-portals. 


# IMPORTANT: These configuration files will work on Hyprland 0.23 version.

### Copy Configuration and stuff
1. Copy the contents of config to .config
2. Copy the content of etc to your /etc folder. Don't copy the folder and paste it into /etc! It will break the system. Copy the content.
3. Copy the contents of usr to the respective folders fo /usr/share folder. Don't copy the folder and paste into /usr/share! It will also break your system. Copy the contents to the respective folder.
4. If you are going to use Hyprland only then add these lines to /etc/environment

``` bash
MOZ_ENABLE_WAYLAND=1
QT_QPA_PLATFORMTHEME=qt5ct
QT_QPA_PLATFORM=wayland
QT_WAYLAND_DISABLE_WINDOWDECORATION=1
QT_AUTO_SCREEN_SCALE_FACTOR=1
```
Reference:
1. https://github.com/hyprwm/Hyprland
2. https://wiki.hyprland.org/
3. https://github.com/wildan-pratama/wildan-hyprland
4. https://github.com/arcolinux/arcolinux-hyprland
