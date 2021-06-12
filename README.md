# Blackpanther-arch-rice
A guide to replicating my riced Arch Linux set-up. 
## What You'll Be Creating Today

![The Setup](https://github.com/kavirakesh14/blackpanther-arch-rice/blob/master-branch/screenshots/lockscreen.png)

![The Setup](https://github.com/kavirakesh14/blackpanther-arch-rice/blob/master-branch/screenshots/home.png)

![The Setup](https://github.com/kavirakesh14/blackpanther-arch-rice/blob/master-branch/screenshots/powermenu.png)

It's my personal setup and what I'm using at the time of writing. If you want more, this guide will teach you the basics and provide a set-up to 'improve' on with your own needs in mind.

Visit [r/unixporn](https://www.reddit.com/r/unixporn/) to see what others have created.

## Lets Get Cooking!

### Guide Dependencies

Before we get to the ricing, we need to install a few things first.

#### Install basic apps

`sudo pacman -S dmenu vim rofi ranger feh`

To use Dmenu, press `mod+d`. Only packages that have a GUI will appear if selected through Dmenu, otherwise it'll seem as if it's not working. This is normal.

To Use Ranger, run `ranger`.

#### Install Yay

```
cd ~
mkdir -p /tmp/yay_install
cd /tmp/yay_install

sudo pacman -S base-devel

sudo pacman -S expac yajl git

git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si

cd ~
rm -r /tmp/yay_install
```
#### Wallpaper
```
cd ~
mkdir -p ~/Pictures
mv ~/blackpanther-arch-rice/wal ~/Pictures
```
#### Install Polybar

First you'll need to install the dependencies and then Polybar itself:
```
sudo pacman -S cairo libxcb python2 xcb-proto xcb-util-image xcb-util-wm xcb-util-xrm jsoncpp
yay -S polybar-git
```
#### Install Dot Files

```
cd ~
git clone https://github.com/kavirakesh14/blackpanther-arch-rice.git
cp -r ~/blackpanther-arch-rice/config/ ~/

cp -r ~/blackpanther-arch-rice/.Xdefaults ~/
```
Refresh i3 by pressing mod+r.

Only terminals and windows opened after this point will have those two changes applied to them.
#### Install Fonts

`yay -S otf-nerdfonts`

Refresh i3 to load changes.

## Make Changes To i3 Config
Read through the whole config file and understand what's happening. Change anything that's necessary. The comments will give you hints as to what you may want to change. Do not skip this step. It'll teach you got to use i3.

### Neofetch System Info and Replace ASCII Logo With Image

`neofetch --w3m --source ~/Pictures/wal/icon2.jpg`

To customise what is displayed when you run `neofetch` or the above command, comment in/out lines in `~/.config/neofetch/config`

## Done!

Your set up should be identical to mines now.
