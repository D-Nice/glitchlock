```
 ┏━┓┳  o┏┓┓┏━┓┳ ┳┳  ┏━┓┏━┓┳┏ 
 ┃ ┳┃  ┃ ┃ ┃  ┃━┫┃  ┃ ┃┃  ┣┻┓
 ┇━┛┇━┛┇ ┇ ┗━┛┇ ┻┇━┛┛━┛┗━┛┇ ┛

```

glitchlock: a glitch art themed randomized lockscreen. powered by i3lock-color.

![glitchlock preview](https://raw.githubusercontent.com/xero/glitchlock/master/preview.png)

(note, the lock screen **IS** animated, but is also slow. Takes ~5 seconds on average to run on an intel core 2 duo p8400, can lower glitches count, or other performance improvements welcomed)

## table of contents
* [about](#about)
* [how it works](#how-it-works)
* [security](#security)
* [requirements](#requirements)
* [customize](#customize)
* [more](#more)
* [license](#license)

### about (original)

i do [glitch art](https://x-ero.tumblr.com) for fun. i was messing around w/ one of my shell scripts and thought: this would make a cool lockscreen! after a bit of research and refactoring here we are.

### about (fork)

creates a number of images, that can be used in a slideshow configuration to make the screen look like it's in fact glitching out.

removed GLITCHICON.

credits to reddit users ----E---- and inu7el for some ideas borrowed in this script (slideshow & dd efficiency respectively)

### how it works

the script takes a screenshot, then datamoshes a slideshow of it.

### security

this lockscreen has the potential for information leakage, since it uses a screenshot of your active screen. i made this for fun and personal use, please take care and weigh your opsec and personal threat model before deciding to use this (consider pixelation?).

an example workaround would be setting up your screen very nicely w/o any secret info in it and taking a screenshot. then replace [line #9](https://github.com/xero/glitchlock/blob/master/glitchlock#L9) in the script (`scrot /tmp/lock.png`) with a command to {move,copy} your pre-setup screenshot into place (e.g. `cp ~/lib/img/lock.png /tmp/lock.png`) then let the script randomly glitch that image out everytime.

### requirements

* i3lock-color (with merged slideshow PR)
	* the "ricing" fork of the lockscreen application
	* https://github.com/PandorasFox/i3lock-color
* scrot
	* the premiere nix screen shot tool
	* https://github.com/dreamer/scrot
* imagemagick
	* image manipulation toolkit
	* https://github.com/ImageMagick/ImageMagick

if you're using [arch](https://www.archlinux.org) they can all be installed from the extra, community, and aur repos:

`yay -S i3lock-color-git scrot imagemagick`

\* [yay](https://github.com/Jguer/yay) is an aur helper that wraps [pacman](https://www.archlinux.org/pacman/).

### customize

if called alone, the script will take a screenshot and glitch it. 
an example of calling the script on `MOD4+ESC` using [sxhkd](https://github.com/baskerville/sxhkd)

```
# lockscreen
mod4 + Escape
 ~/bin/glitchlock
```

### more

* https://0w.nz
* https://xero.nu
* https://nixers.net
* https://git.io/.files
* https://reddit.com/r/unixporn

## license

![kopimi logo](https://gist.githubusercontent.com/xero/cbcd5c38b695004c848b73e5c1c0c779/raw/6b32899b0af238b17383d7a878a69a076139e72d/kopimi-sm.png)

[kopimi](https://kopimi.com)! in the spirit of _freedom of information_, i encourage you to fork, modify, change, share, or do whatever you like with this project! `^c^v`
