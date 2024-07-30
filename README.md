# Hayden's DWM (HDWM)

This is a version of DWM made to work with my [NixOS configuration](https://github.com/hayden-donnelly/dotfiles). You can probably use it for your own system (if you want), but keep in mind that you'll have to install the runtime programs for everything to work correctly. You'll also have to change the `MY_HOME_PATH` macro in `config.def.h` to your own username (i.e. `#define MY_HOME_PATH(path) "/home/<your-username>/"path`). This is used for accessing the user's home directory from autostart since relative paths don't work.

## Build Dependencies
- Xlib header files

## Runtime Programs
HDWM assumes that these programs are installed and makes use of them at runtime.
- Flameshot
- Kitty
- Dmenu
- Feh

## Wallpaper
To set the wallpaper, place the wallpaper image you want in your user's home directory, rename it to `.wallpaper.png`, then restart DWM.

## Original Readme
This is the original readme text for DWM.
```
dwm - dynamic window manager
============================
dwm is an extremely fast, small, and dynamic window manager for X.


Requirements
------------
In order to build dwm you need the Xlib header files.


Installation
------------
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install


Running dwm
-----------
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm


Configuration
-------------
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
```
