# Setup-SSH-Key
Setup SSH Key-based Authentication on a Linux Server

## Pre-requisites
* A Linux server (tested with Centos 7)
* A local computer (tested on Mac Pro)

## Introduction of SSH Key
Please refer to this [page](https://www.digitalocean.com/community/tutorials/how-to-configure-ssh-key-based-authentication-on-a-linux-server)

## Create SSH Key
Open a terminal on your local computer, and generate a SSH key pair by typing:
```
$ ssh-keygen
```
Then it will prompt you to select a location for the keys:
```
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/username/.ssh/id_rsa):
```
Press `ENTER`, keeping the default location.

If the key areadly exists, you'll see the prompt:
```
/Users/username/.ssh/id_rsa already exists.
Overwrite (y/n)? n
```
Press `n` by using the existing key pair. They should be store at 
`/Users/username/.ssh/id_rsa` (private key) and `/Users/username/.ssh/id_rsa.pub` (public key)

If generate a new key pair, it will prompt:
```
Created directory '/home/username/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again: 
```
Press `ENTER` to bypass this setting, otherwise you may have to provide it everytime you use this key.

Finally, you'll see prompt like:
```
Your identification has been saved in /Users/username/.ssh/id_rsa.
Your public key has been saved in /Users/username/.ssh/id_rsa.pub.
The key fingerprint is:
a9:49:2e:2a:5e:33:3e:a9:de:4e:77:11:58:b6:90:26 username@remote_host
The key's randomart image is:
+--[ RSA 2048]----+
|     ..o         |
|   E o= .        |
|    o. o         |
|        ..       |
|      ..S        |
|     o o.        |
|   =o.+.         |
|. =++..          |
|o=++.            |
+-----------------+
```

You now have a public and private key that you can use to authenticate. The next step is to place the public key on your server so that you can use SSH key authentication to log in.

## Place the Public Key on the Server
On your local computer, you can check the pulic key:
```
$ cat ~/.ssh/id_rsa.pub
```
```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCb+3pH0GS9eskv+9A7MAeQjoGHiVAkdOSKOjwy+vEE6Q0qUkiYFi2o4dJUH08xcxR5hPUkz3LRYf+c1zm+YGmFjilkEjyOyZ1EpeK26D5d7GKOj8/hq2QU2fPGX6ZMJ9JlsHp7Thn8bNjTj0HJjtH+W4abuxA7cYN2SizEHFLv3xQjig/B/n2p7EukSsL03ISnJfWVNM7T6oWg6CTenBUo3r/2RLFZF+xaiHZacVZcE1O/dqTXqj3L3+vMCEyHA0ScoIlQ6pYqgzcC5IGHcAbD9K6Dl04nVq/dnnUwKoFY4aUWmsJq7efq245gAuHa02Qycwopdf+dcqhjDly6vQc1 username@MacBook-Pro.local
```
Copy and paste the public key to the server: `~/.ssh/authorized_keys`
