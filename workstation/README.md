# Configure Workstation

## Install Ubuntu

*  Download **_64-bit Ubuntu 18.04_** to create a bootable disk from a USB stick.
*  Install Ubuntu from the bootable USB.
*  If you are dual booting, give the Windows partition at most _100 GB_ disk space and give the rest to Ubuntu.
*  Create the default Ubuntu user 
*  Once installation is complete, make sure your internet connection is working properly.
*  Now run upgrade.

```console
$ sudo apt-get update
$ sudo apt-get upgrade
```

* Increase [file watcher numbers](https://github.com/gulpjs/gulp/issues/217). This is needed for gulp and Intellij IDEA.

```
$ echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

## Install Google Chrome

Download the 64-bit *.deb file from [https://www.google.com/chrome/browser/desktop/](https://www.google.com/chrome/browser/desktop/). Then install using the the following command:

```console
$ cd ~/Download
$ sudo dpkg -i <deb_file_name>.deb
$ sudo apt-get install -f
$ rm <deb_file_name>.deb
```

### Install Chrome Extensions
- [Refined GitHub](https://chrome.google.com/webstore/detail/refined-github/hlepfoohegkhhmjieoechaddaejaokhf?hl=en)
- [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=en)

## Install Zoom

Download Ubuntu 64 bit 14.04+ debian package from https://zoom.us/download. Then install using the the following command:

```console
$ cd ~/Download
$ sudo dpkg -i zoom_amd64.deb
$ sudo apt-get install -f
$ rm zoom_amd64.deb
```

## Install Ubuntu packages

```console
$ sudo apt-get update
$ sudo apt-get install -y software-properties-common apt-transport-https \
  linux-tools-common linux-tools-generic linux-tools-$(uname -r) \
  build-essential automake \
  terminator fish curl tree rlwrap gnome-tweak-tool httpie \
  graphviz libappindicator1 subversion mercurial \
  python-dev python-setuptools python-pip
```

## Install Better Terminal

```console
$ sudo apt-get install terminator
```

This terminal software allows to split the window vertically and horizontally. This is very handy when working with big screens.

## Install Sublime Text 4

https://www.sublimetext.com/docs/linux_repositories.html#apt

```console
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
sudo apt-get update
sudo apt-get install sublime-text
```

To upgrade an existing installation, run

```console
$ sudo apt-get install --only-upgrade sublime-text-installer
```

## Install Visual Studio Code

Visual Studio Code is simple IDE with powerful language specific extensions. 
Download the 64-bit *.deb file from [its website](https://code.visualstudio.com/download) and install it.

## Install Postman

Postman is a free GUI tools for developing and testing HTTP apis. Download and install it from their website https://www.getpostman.com/apps

## Configure Alias

### Bash

```
$ nano ~/.bashrc

alias gg="git gui"
alias gs="git status"
alias gm="git checkout master;git pull origin master"
alias gp="git add .;git commit -a -s -m added-all;git push origin HEAD"
alias g2h="git push origin HEAD"
alias gr="git reset --hard HEAD"
alias gmv="go mod tidy; go mod vendor"
alias ga="git add .;git commit --amend --no-edit -a -s"
```

### Fish

```
$ nano ~/.config/fish/config.fish

alias gg 'git gui'
alias gs 'git status'
alias gm 'git checkout master;git pull origin master'
alias gp 'git add .;git commit -a -s -m added-all;git push origin HEAD'
alias g2h 'git push origin HEAD'
alias gr 'git reset --hard HEAD'
alias gmv 'go mod tidy; go mod vendor'
alias ga 'git add .;git commit --amend --no-edit -a -s'
```

## Troubleshooting

### Pulse Audio Profile

`sudo vi /usr/share/pulseaudio/alsa-mixer/profile-sets/default.conf`

```
; An example for defining multiple-sink profiles
[Profile output:analog-stereo+output:hdmi-stereo+input:analog-stereo]
description = Analog Stereo
output-mappings = analog-stereo hdmi-stereo
input-mappings = analog-stereo
```
