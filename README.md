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
Enter file in which to save the key (/Users/zhifei/.ssh/id_rsa):
```
Press `ENTER`, keeping the default location.
