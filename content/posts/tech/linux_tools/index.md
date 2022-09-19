---
weight: 1
title: "Useful Linux Tools"
lastmod: 2022-09-19 20:34:56
draft: false
author: ""
description: "Useful Linux Tools"
images: []

tags: ["tech",]
categories: ["tech"]

lightgallery: true
fontawesome: true

toc:
  enable: false
  auto: false
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
  # ...
mapbox:
  # ...
share:
  enable: false
  # ...
comment:
  enable: false
---


# My basic linux setup

1) ssh into the server and paste the github private key (or create a new pair):
```
ssh-keygen -t rsa
```
2) Edit .ssh/config:
```
echo "
Host github.com
  HostName github.com
  User skoricius
  IdentityFile ~/.ssh/id_rsa
 " >> ~/.ssh/config
 ```
2) Clone the git repository
```
git init ~/
git remote add origin git@github.com:Skoricius/linux_setup.git
git fetch
git checkout -t origin/master
```
3) Run parts of the scripts/linux_setup.sh that you require. 
The basic ones are `install_apt.sh` that installs some basic utilities that I like to use.
Then, I use `set_up_neovim.sh` and `set_up_zsh.sh` for neovim editor and zsh shell.

# Using telegram bot

Based on my [telegram_bot](https://github.com/Skoricius/telegram_bot) repository.

Add token and chat id environmental variables to `.zshrc`:

```bash
export TELEGRAM_TOKEN=<token>
export TELEGRAM_CHAT_ID=<chat_id>
```

Copy `telegram` binary to a folder in your path `cp telegram /usr/bin`.

Run with `telegram <message>`.

# Useful commands

## Reverse ssh
```
ssh -N -L 8001:localhost:8888 luka@dreams-ai.com
```

(local-port:remote-port server-address)

## Setting up ssh key
```
ssh-keygen -t rsa -f ~/.ssh/id_rsa
ssh-copy-id -i $HOME/.ssh/id_rsa.pub user@server
```
Add ssh key to ~/.ssh/config:
```
 echo "
Host dreams-config
  HostName dreams-ai.com
  Port 222
  User root
  IdentityFile ~/.ssh/id_rsa_steve
" >> ~/.ssh/config
```

## Transferring files
Using rsync (faster than sftp and only transferres deltas)
```
rsync -azP <remote_host>:<remote_folder> <local_folder>
```

For a file server, this is a nice utility: https://github.com/sigoden/duf
Just download the binary and run: `duf -b 0.0.0.0` and remember to allow the port through a firewall:
`sudo ufw allow 5000`

### Google Drive

For Google drive sync from terminal, use [gdrive](https://github.com/prasmussen/gdrive).
```
go install github.com/prasmussen/gdrive@latest
```

And then:
- Upload: `gdrive upload <file>`
- Download: `gdrive download <file_id>`
- To find file ID: `gdrive list --query " '<folder_id>' in parents"`. Folder ID is the last bit of the URL when you navigate to that folder.

## Setting up VPN on a private server
https://github.com/StreisandEffect/streisand

## Markdown to pdf
grip <filename>.md
  
## Downloading podcasts and youtube
youtube: https://ytdl-org.github.io/youtube-dl/index.html
podcasts: https://github.com/brtmr/podfox

## Mapping network drive (cmd)
net use z: \\remotepc\sharename