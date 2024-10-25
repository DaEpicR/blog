---
title: 'How to connect to wifi inside arch install'
description: 'using `iwctl` built in tool in archinstall iso '
publishedDate: 2024-02-21
tags:
  - Linux
  - Guide
---

![](/public/bluescreen.png)

#### You've propably heard the term "I use arch btw", wich is a bit annoying but understandable, but while trying to install 'arch', you'll incounter a network issue if you don't use **Ethernet Cable** , no internet mean no arch :(, well the solution is pretty easy and stright forward:

#### Just run these command in the same order and you'll get it working

> You're already in root so no need for `sudo`.

> run `ip link`

1. `systemctl enable iwd`
2. `rfkill unblock all`

> Run `ip link` to see your network interface name

3. `iwctl`

### Now you're in a Terminal based network manager

---

> in this case mine is `wlan0`

4. `iwctl`
5. `station list`
6. `station wlan0 scan`
7. `station wlan0 get-networks`
8. `station wlan0 connect 'type your network name {SSID} and hit tab to auto complete'`
