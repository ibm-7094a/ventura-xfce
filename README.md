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
```
In the event you choose to remove lightpad: 
```
sudo ninja uninstall
```
#### GTK Themes & Icons
##### Installing Themes
```
mkdir .themes
cp ~/ventura-xfce/gtk/gtkthemes/WhiteSur-Light.tar.xz ~/.themes/
tar -xvf ~/.themes/WhiteSur-Light.tar.xz
cp ~/ventura-xfce/gtk/gtkthemes/WhiteSur-Dark.tar.xz ~/.themes/
tar -xvf ~/.themes/WhiteSur-Dark.tar.xz
```
##### Installing Icons
```
mkdir .icons
cp ~/ventura-xfce/gtk/icons/01-WhiteSur.tar.xz ~/.icons/
tar -xvf ~/.icons/01-WhiteSur.tar.xz
cp ~/ventura-xfce/gtk/icons/custom.tar.xz ~/.icons/
tar -xvf ~/.icons/custom.tar.xz
```
##### Installing Cursor Theme
```
cp ~/ventura-xfce/cursors/WhiteSur-cursors.tar.xz ~/.icons/
tar -xvf ~/.icons/WhiteSur-cursors.tar.xz
```
#### Plank
From your current launcher of choice, start plank
Open Window Manager Tweaks, on the upper right, select compositor, & uncheck 'Show shadows under dock windows'
Press CTRL+ALT+T to initialize a terminal window
**Navigate to the Dock folder**
```
cd ~/ventura-xfce/dock/
```
copy all dock launchers to a hidden folder
```
cp launchers/ ~/.launchers -r
```
switch to that directory
```
cd /home/YOUR_USERNAME/.launchers/
```
replace my username with yours in every launcher (case sensitive)
```
sed -i 's/ibm-7094/YOUR_USERNAME/g' *
```
Once that's done, open thunar
```
thunar
```
now drag all launcher files onto the plank window

#### Wallpapers
```
cp ~/ventura-xfce/wallpapers/ ~/.wallpapers
```
If wallpapers do not appear on login, right click on desktop & select
Desktop Settings > Background > Folder > Other > /home/YOUR_USERNAME/.wallpapers/
#### Panel
```
sudo cp ~/ventura-xfce/config/xfce4/ ~/.config/xfce4 -r
sudo cp ~/ventura-xfce/config/xfce4-dict/ ~/.config/xfce4-dict -r
```
## To Finish, Restart Your Computer & Log Back Into XFCE

#### DEBLOAT
All of the above was written under the assumption that you want to keep copies of everything.
If this is not the case, execute the code below.
```
rm -rf ~/ventura-xfce
rm -rf ~/.themes/WhiteSur-Light.tar.xz
rm -rf ~/.themes/WhiteSur-Dark.tar.xz
rm -rf ~/.icons/01-WhiteSur.tar.xz
rm -rf ~/.icons/custom.tar.xz
rm -rf ~/.icons/WhiteSur-cursors.tar.xz
```

   [ventura-xfce]: <https://github.com/ibm-7094a/ventura-xfce>
   [WhiteSur-icons]: <https://github.com/vinceliuice/WhiteSur-icon-theme>
   [WhiteSur-gtk]: <https://github.com/vinceliuice/WhiteSur-gtk-theme>
   [BigSurIcons]: <https://bigsuricons.webflow.io/?ref=producthunt>
   [Lightpad]: <https://github.com/libredeb/lightpad>
