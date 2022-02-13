# Git

Watch/read these links in order and practice in your personal git repository at the same time. You should memorize the basic git commands and their usage.

## Install git

```console
$ sudo apt-get install git git-gui
```
### Configure git

```console
$ git config --global user.name <your-name>
$ git config --global user.email <your-email@appscode.com>
```

### Git ignore .DS_Store

- https://0xmachos.com/2020-01-22-Eradicating-.DS_Store-From-Git/

```console
$ echo .DS_Store > ~/.gitignore

$ git config --global core.excludesfile ~/.gitignore
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

## Video Tutorials

- [Git tutorial by Sajib](https://www.youtube.com/watch?v=7orfDC1ALvs)

## Learn Git
[Pro Git](https://git-scm.com/book/en/v2) is the best book on Git. It is written by one of the cofounders of GitHub. Read ch 2 and 3 to get started. I recommend reading the whole book if you are interested.

- [Git Basics](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)
- [Git Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)

## Git branching game
- https://learngitbranching.js.org/

## Additional Resources
- https://try.github.io/levels/1/challenges/1
- [Git Tutorial for Beginners: Command-Line Fundamentals](https://www.youtube.com/watch?v=HVsySz-h9r4)
- [Git Tutorial: Fixing Common Mistakes and Undoing Bad Commits](https://www.youtube.com/watch?v=FdZecVxzJbk)
- [Git Tutorial: Using the Stash Command](https://www.youtube.com/watch?v=KLEDKgMmbBI)

