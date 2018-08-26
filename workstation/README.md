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
- [Sourcegraph](https://chrome.google.com/webstore/detail/sourcegraph/dgjhfomjieaadpoljlnidmbgkdffpack?hl=en)
- [Refined GitHub](https://chrome.google.com/webstore/detail/refined-github/hlepfoohegkhhmjieoechaddaejaokhf?hl=en)

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

## Install Sublime Text 3

```console
$ wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
$ sudo apt-get install apt-transport-https
$ echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
$ sudo apt-get update
$ sudo apt-get install sublime-text
```

To upgrade an existing installation, run

```console
$ sudo apt-get install --only-upgrade sublime-text-installer
```

## Install Visual Studio Code

Visual Studio Code is simple IDE with powerful language specific extensions. 
Download the 64-bit *.deb file from https://code.visualstudio.com/download and install it.

## Install git

```console
$ sudo apt-get install git git-gui
```
### Configure git

```console
$ git config --global user.name <your-name>
$ git config --global user.email <your-email@appscode.com>
```

### Configure `ssh` keys

1. **Ensure you have an SSH client installed**: Open a terminal on your local system and enter the following command to identify which version of SSH you have installed.

```console
$ ssh -v
OpenSSH_5.6p1, OpenSSL 0.9.8r 8 Feb 2011
usage: ssh [-1246AaCfgKkMNnqsTtVvXxYy] [-b bind_address] [-c cipher_spec]
           [-D [bind_address:]port] [-e escape_char] [-F configfile]
           [-I pkcs11] [-i identity_file]
           [-L [bind_address:]port:host:hostport]
           [-l login_name] [-m mac_spec] [-O ctl_cmd] [-o option] [-p port]
           [-R [bind_address:]port:host:hostport] [-S ctl_path]
           [-W host:port] [-w local_tun[:remote_tun]]
           [user@]hostname [command]
```

2. **Set up your default identity**: Now, open a terminal in your local system and run `ssh-keygen`. Press ENTER 3 times to accept default options.

```console
$ ssh-keygen -t rsa -C "<your-email>"
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/manthony/.ssh/id_rsa): 
Created directory '/Users/manthony/.ssh'.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/manthony/.ssh/id_rsa.
Your public key has been saved in /Users/manthony/.ssh/id_rsa.pub.
The key fingerprint is:
4c:80:61:2c:00:3f:9d:dc:08:41:2e:c0:cf:b9:17:69 manthony@myhost.local
The key's randomart image is:
+--[ RSA 2048]----+
|*o+ooo.          |
|.+.=o+ .         |
|. *.* o .        |
| . = E o         |
|    o . S        |
|   . .           |
|    .            |
|                 |
|                 |
+-----------------+
```

3. **Start the ssh-agent and load your keys**: 

* Open a terminal window and enter the following command to see if the agent is running:

```console
$ ps -e  | grep [s]sh-agent
9060 ??         0:00.28 /usr/bin/ssh-agent -l
```

* If the agent isn't running, start it manually with the following command:

```console
$ ssh-agent /bin/bash
```

* Load your new identity into the ssh-agent management program using the ssh-add command.

```console
$ ssh-add ~/.ssh/id_rsa
Enter passphrase for /Users/manthony/.ssh/id_rsa: 
Identity added: /Users/manthony/.ssh/id_rsa (/Users/manthony/.ssh/id_rsa)
```

* Use the ssh-add command to list the keys that the agent is managing.

```console
$ ssh-add -l
2048 7a:9c:b2:9c:8e:4e:f4:af:de:70:77:b9:52:fd:44:97 /Users/manthony/.ssh/id_rsa (RSA)
```

5. **Install the public key on your Github account**

* Open a browser and log into Github.
* Choose **avatar > Your profile** from the application menu. 
* The system displays the **Personal settings** page.
* Click **SSH keys**.
* The **SSH Keys** page displays. It shows a list of any existing keys. Then, below that, a dialog for labeling and entering a new key.
* Back in your terminal window, copy the contents of your public key file.
* For example, in Linux you can cat the contents.

```console
$ cat ~/.ssh/id_rsa.pub
```
* Back in your browser, enter a Label for your new key, for example, Default public key.
* Paste the copied public key into the SSH Key field:

![alt_text](/images/github-keys.png)

* Press Add key.
* The system adds the key to your account.

## Install Postman

Postman is a free GUI tools for developing and testing HTTP apis. Download and install it from their website https://www.getpostman.com/apps

