#For personal branch
##Brightness button done
- install brightnessctl
- for Arch: sudo pacman -S brightnessctl
##volume button done
##sallow patch done
Dependencies on suckless site:  
- libxcb
- Xlib-libxcb
- xcb-res
For Arch: sudo pacman -S libxcb xcb-util
##Better fonts
For Arch: sudo pacman -S terminus-font


# BABA's DWM Build
### Patches use in this build for extending dwm functionality
1. [pertag](https://dwm.suckless.org/patches/pertag/) This patch keeps layout, mwfact, barpos and nmaster per tag.  
2. [alwayscenter](https://dwm.suckless.org/patches/alwayscenter/) All floating windows are centered, like the center patch, but without a rule.  
3. [attachbottom](https://dwm.suckless.org/patches/attachbottom/) New clients attach at the bottom of the stack instead of the top.  
4. [warp](https://dwm.suckless.org/patches/warp/) This patch warps the mouse cursor to the center of the currently focused window or screen when the mouse cursor is (a) on a different screen or (b) on top of a different window. In simple terms keep mouse cursor on selected window.  
5. [fakefullscreen](https://dwm.suckless.org/patches/fakefullscreen/) Only allow clients to "fullscreen" into space currently given to them. As an example, this will allow you to view a fullscreen video in your browser on one half of the screen, while having the other half available for other tasks.  
6. [functionalgaps](https://dwm.suckless.org/patches/functionalgaps/) Functionalgaps combines the beautifully simplistic gaps of [fullgaps](https://dwm.suckless.org/patches/fullgaps/) with the non-gaps of [singularborders](https://dwm.suckless.org/patches/singularborders/) and [noborder](https://dwm.suckless.org/patches/noborder/). It is named functionalgaps because, since gaps are purely aesthetic, and therefore not useful whatsoever, this patch adds to their functionality by allowing them to easily be turned off. This patch is also unique because of its out of the box integration with [pertag](https://dwm.suckless.org/patches/pertag/), allowing gaps to be enabled/disabled and sized on a per-tag basis.  

# Screenshot
![screenshot](https://user-images.githubusercontent.com/100849131/188226247-c7b77536-93db-4f7b-9a0b-867efa799477.png)

# Keybindings/Shortcuts
### By default Mod-key is Windows-key
| Key | Description |
| --- | --- |
|[Mod] + [Shift] + [=]|Toggle Gaps|
|[Mod] + [Shift] + [-]|Reset Gaps|
|[Mod] + [+]|Increase Gaps|
|[Mod] + [-]|Decrease Gaps|
|[Shift] + [Mod] + [Enter]|launch terminal|
|[Mod] + [b]|show/hide bar|
|[Mod] + [p]|dmenu|
|[Mod] + [Enter]|push acive window from stack to master, or pulls last used window from stack onto master|
|[Mod] + [j / k]|focus on next/previous window in current tag|
|[Mod] + [h / l]|increases / decreases master size|
|[Mod] + [2]|moves your focus to tag 2|
|[Shift] + [Mod] + [2]|move active window to the 2 tag|
|[Mod] + [i / d]|increases / decreases number of windows on master|
|[Mod] + [, / .]|move focus between screens (multi monitor setup)|
|[Shift] + [Mod] + [, / .]|move active window to different screen|
|[Mod] + [0]|view all windows on screen|
|[Shift] + [Mod] + [0]|make focused window appear on all tags|
|[Shift] + [Mod] + [c]|kill active window|
|[Shift] + [Mod] + [q]|quit dwm|
|[Mod] + [t]|tiled mode []=|
|[Mod] + [f]|floating mode ><>|
|[Mod] + [m]|monocle mode [M] (single window fullscreen)|
|[Mod] + [RightMouseButton]|to resize the floating window|
|[Mod] + [LeftMouseButton]|to move the floating window around|
|[Mod] + [Space]|toggles to the previous layout mode|
|[Mod] + [Shift]+[Space]|to make an individual window float|
|[Mod] + [MiddleMouseButton]|to make an individual window un-float|

# Install
### Note
- If you can compile bare bone dwm, you can compile this too. NO extra dependencies needed.
### Requirements
- [st](https://st.suckless.org/) - simple/suckless terminal  
- [dmenu](https://tools.suckless.org/dmenu/) - dynamic menu for X, originally designed for dwm.

### Dependencies for DWM
- On Arch Linux:

```
sudo pacman -S base-devel libx11 libxft libxinerama freetype2 fontconfig
```

- On Debian:

```
sudo apt install build-essential libx11-dev libxft-dev libxinerama-dev libfreetype6-dev libfontconfig1-dev
```

- On OpenBSD:
if Xenocara is installed, dependencies are already met.

- On Void Linux (case sensitive):

```
sudo xbps-install base-devel libX11-devel libXft-devel libXinerama-devel freetype-devel fontconfig-devel
```

### After installing dependencies run step by step this commands on terminal

```
mkdir suckless && cd suckless && git clone https://github.com/dixitdeveloper/dwm.git
```

- If you already have st and dmenu installed on system you can skip this step

```
git clone https://git.suckless.org/st && git clone https://git.suckless.org/dmenu && cd st && sudo make clean install && cd ../dmenu && sudo make clean install && cd ../
```
- now it's time to compile dwm

```
cd dwm && sudo make clean install
```

- If you find any error just search on google dwm compilation dependencies according to your destro and install them on your system and compile dwm again. You good to go.
- Because of dependencies problem we did't include [swallow](https://dwm.suckless.org/patches/swallow/) patch.
- Again, If you can compile bare bone dwm, you can compile this too. NO extra dependencies needed.

# Use DWM with Display Manager

- Go to
 
```
cd /usr/share/xsessions
```

- Create desktop file

```
sudo touch dwm.desktop
```

- Put This content in dwm.desktop file

```
[Desktop Entry]
Encoding=UTF-8
Name=Dwm
Comment=Dynamic window manager
Exec=/usr/local/bin/dwm
Icon=dwm
Type=XSession
```
- Now loged out

# Use DWM with startx
- If you’re using startx, simply add **exec /usr/local/bin/dwm** or **exec dwm** at the end of your .xinitrc file on Linux, or at the end of your .xsession file on OpenBSD.

# Last step
## Change Fonts, make some configration and MAKE IT YOURS
