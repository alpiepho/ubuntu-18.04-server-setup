# ubuntu-18.04-server-setup
Notes and tools to set up Ubuntu 18.04 development system with KVM etc.  This is my chcklist for setting up Unbuntu for using ad a dev system and KVM, Docker, Ancible, etc.

## Create USB Stick with Ubuntu 18

To install Ubuntu:

- download Ubuntu [here](http://releases.ubuntu.com/)
- on Mac, used ["Etcher"](https://www.balena.io/etcher/) to burn image
- (tried use micro SD for Raspberry Pi in holder, but that failed, recooment USB stick)
- boot PC/Notebook with SD card inserted
- might need hardware Setup keys to boot from usb
- run thru normal install
- did not configure Wifi or download during install (for simplicity)

## After the Install and First Boot

- (Wifi Settings from top right) enable wifi and enter credentials
- (from Settings app) disable various power settings
- (Gui) software update
- (terminal) sudo apt-get update
- (terminal) sudo apt-get upgrade

## Configure Display etc.

## Install Basic Tools

- Chrome
- VS Code


## Install VNC Remote Desktop

## Install VPN

## Install KVM

## Install Docker

## Install Arduino IDE


## Install Node and Puppeteer


## TODO List for Other Setup

<pre>


install kvm:
https://help.ubuntu.com/community/KVM/Installation
need to relogin for groups

enable vnc:
gui settings - sharing
click on Screen Sharing, set password and network

from:
https://ubuntuforums.org/showthread.php?t=2391847
gsettings set org.gnome.Vino require-encryption false



TODO:
add these notes to github, reformat as README.md
prompt
install code
https://code.visualstudio.com/docs/setup/linux

install chrome
google chrome, download, run it

vpn
https://getoutline.org/en/home


different desktops (try on kvm first)

enable vnc (there is a trick that I cannot recall)

setup kvm for kali (or virtualbox?)

install and try ansible

node

puppetteer?

arduino from linux?
https://www.arduino.cc/en/guide/linux
arduino from vsocde


via vscode?


change display (for use with vnc)
https://www.bonusbits.com/wiki/HowTo:Add_Missing_or_Custom_Display_Resolution_on_Ubuntu


</pre>
