# ventura-xfce
## _MacOS Ventura in XFCE_
#### _A Simple Recreation For Apple Fanatic Developers_

Ventura-XFCE is my take on the beautiful MacOS desktop
recreated in the XFCE Desktop Environment.
**It should be noted that as of latest commit, the project only officially supports debian-based distros**

- It uses about 600 Megabytes of RAM on it's lowest settings
- Fully Nord-Compatible
- Incorporates ACTUAL MacOS icons into panels, docks, & more

## Features

- MacOS GTK theme including windows & buttons
- Launchers for non-Mac apps that mock appmenu behavior & name
- Confuses actual Mac users (assuming they don't stare at your appmenu on the Desktop)
- Semi-transparent Applications Menu & Terminal
- (Optional) Custom Login Page!


> "I truly enjoy the appearance of Apple's Mac Operating System,
> but have found myself unable to enjoy proprietary softwares whose
> code isn't available to the public!"
> . .   .
> -IBM-7094
> (On a day he was frustrated with his dracula theme & candy icons)

## Credits

ventura-xfce uses a number of open source projects to work properly:

- [WhiteSur-gtk] - vinceliuice's Big Sur-esque theme for gtk Desktop Environments
- [WhiteSur-icons] - vinceliuice's Big Sur-esque icons
- [Lightpad] - Libredeb's Wayland-Compatible applauncher, originally created for TwisterOS
- [BigSurIcons] - Ripped copies of several MacOS icons

And as you might expect, ventura-xfce is also a  [public repository][ventura-xfce]
 on GitHub.

## Dependencies

Debian-Based Distros:
```
sudo apt-get install meson ninja-build libgee-0.8-dev libgnome-menu-3-dev cdbs valac libvala-*-dev libglib2.0-dev libwnck-3-dev libgtk-3-dev xterm python3 python3-wheel python3-setuptools gnome-menus plank xfce4-appmenu-plugin
```
## Installing & Configuring Ventura-Xfce
Clone This Repo!
```
git clone https://github.com/ibm-7094a/ventura-xfce
cd ventura-xfce
```
#### Lightpad
```
cd lightpad
meson build --prefix=/usr
cd build
ninja
sudo ninja install
[in the event you choose to remove lightpad: sudo ninja uninstall]
```
#### GTK Themes & Icons
Open your terminal
```
mkdir .icons
mkdir .themes
sudo cp 
```
#### Plank
From your current launcher of choice, start plank
Open Window Manager Tweaks, on the upper right, select compositor, & uncheck 'Show shadows under dock windows'
Press CTRL+ALT+T to initialize a terminal window
**Navigate to the Dock folder**
```
cd /home/YOUR_USERNAME/ventura-xfce/dock/
# copy all dock launchers to a hidden folder
cp launchers/ /home/YOUR_USERNAME/.launchers -r
# switch to that directory
cd /home/YOUR_USERNAME/.launchers/
# replace my username with yours in every launcher (case sensitive)
sed -i 's/ibm-7094/YOUR_USERNAME/g' *
# Once that's done, open thunar
thunar
# now drag all of those icons into the plank window
```


## License
**Free Software, Hell Yeah!**
Copyright © 2023 ibm-7094

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [ventura-xfce]: <https://github.com/ibm-7094a/ventura-xfce>

