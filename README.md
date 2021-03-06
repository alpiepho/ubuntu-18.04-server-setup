# ubuntu-18.04-server-setup
Notes and tools to set up Ubuntu 18.04 development system with KVM etc.  This is my checklist for setting up Unbuntu for using as a dev system and KVM, Docker, Ancible, etc.

## Create USB Stick with Ubuntu 18

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

The following [link](https://www.bonusbits.com/wiki/HowTo:Add_Missing_or_Custom_Display_Resolution_on_Ubuntu) shows how to add display setting for 1920 1080 resolution.  

The default host name is pretty long and make the default terminal prompt long/complicated.  Looked into chaning the prompt, but found that shortening the host name was easier.  Here is the [link](https://linuxize.com/post/how-to-change-hostname-on-ubuntu-18-04/)


## Install Basic Tools

- Chrome - use Google to find install, very easy
- VS Code - follow [this](https://code.visualstudio.com/docs/setup/linux)


## Install VNC Remote Desktop

Ubuntu 18 already has VNC installed.  You just need to enable it and possible disable encrpytion.

- (Settings app) go to Sharing
- click on Screen Sharing, set password and network
- you may have "encrpytion" errors, if you are certain of your use of VNC behind fireware, can disable this
  - https://ubuntuforums.org/showthread.php?t=2391847
  - or: "gsettings set org.gnome.Vino require-encryption false"


## Install VPN

For some downloads it is nice to use a VPN to further encrpyt the traffic.  I currently use an open source VPN created by "Jigsaw" and sub company of Google.  It is very easy to set up on Digital Ocean and only cost s $5 per month.  This [link](https://getoutline.org/en/home) shows how to install the client software.  You will need to generate a key using the manger app, then cut/paste the key.  WARNING: enabling VPN will break a local VNC session.

## Install KVM

Look at [https://help.ubuntu.com/community/KVM/Installation](https://help.ubuntu.com/community/KVM/Installation). 

Will need to relogin for groups


## Install Virtualbox

I visited numerous websites to install Virtualbox and get it working.  Below are related commands from my history:

<pre>
  ...
  164  wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
  165  wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
  166  sudo add-apt-repository "deb http://download.virtualbox.org/virtualbox/debian bionic contrib"
  167  sudo apt update
  168  sudo apt install virtualbox-6.0
  169  sudo /usr/lib/virtualbox/vboxdrv.sh setup
  170  sudo /sbin/vboxconfig
  171  sudo /sbin/rcvboxdrv setup
  172  sudo apt remove virtualbox-6.0
  173  sudo apt remove virtualbox
  174  sudo apt install virtualbox-6.0
  175  sudo apt-get purge 'virtualbox*'
  176  sudo apt install virtualbox-6.0
  ...
</pre>


## Install Arduino IDE

### Arduino UNO Board
Google arduino from linux and you will find: [https://www.arduino.cc/en/guide/linux](https://www.arduino.cc/en/guide/linux).

Installation was easy.  Did need to follow step to change group on /dev/ttyAMT0.  I aslo had to manually create the /usr/local/bin/arduino symlink, since the install script run from sudo would hang.  (sudo ln -s <path to arduino> /usr/local/bin/arduino
  
You can also run Arduino directly from the VS Code IDE.  Look for the plugin "Ardinuo for VS Code" from Microsoft.  It's a little weird to configure util you realize that opening a .ino file shows controls along the bottom pane.  It does require the default Arduino IDE to be installed.

https://www.arduino.cc/en/guide/linux
arduino from vsocde
</pre>

### Arduino ESP32 Board
This is different board (the step up from the ESP8266) that supports Arduino programming.  On a Mac, this required a legacy driver.  On Linux:

https://github.com/espressif/arduino-esp32/blob/master/docs/arduino-ide/debian_ubuntu.md


## Install Docker

TBD

## Install Node, npm, yarn

I can't recall the web site I found descibing this, but from my history this was very easy:

<pre>
  ...
  132  sudo apt-get update
  133  sudo apt-get install nodejs
  134  sudo apt-get install npm
  135  sudo apt-get install yarn
  ...
  151  sudo apt-get remove cmdtest
  152  curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
  153  echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
  154  sudo apt-get update
  155  sudo apt-get install yarn
  156  yarn -v
  ...
</pre>


## Install Puppeteer

  TBD



## TODO List for Other Setup

- different desktops (try on kvm first)
- setup kvm for kali (or virtualbox?)
- install and try ansible
- puppetteer?
- work in VS Code ssh remore to Centos6 w/o sudo
- get README.md about this and other general Linux stuff




