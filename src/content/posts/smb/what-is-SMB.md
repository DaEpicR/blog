---
title: 'What is SMB'
description: 'What is SMB and how to exploit it'
publishedDate: 2024-10-02
tags:
  - Networking
  - Guide
---

## What is** SMB** ?

**SMB **- **S**erver **M**essage **B**lock Protocol - is a client-server communication protocol used for sharing access to files, printers, serial ports and other resources on a network

The **SMB** protocol is known as a response-request protocol, meaning that it transmits multiple messages between the client and server to establish a connection. Clients connect to servers using **TCP**/**IP** (actually NetBIOS over TCP/IP as specified in RFC1001 and RFC1002), NetBEUI or IPX/SPX.

## How does **SMB** works ?

![](assets/1.png)

## Enumerating **SMB :**

**Tools Used :**

1. SMBclient
2. Nmap

First we start with enumerating open ports :

![](assets/2.png)

Then We use smbclient to try to connect an anon user which is the most common misconfuguration :

![](assets/5.png)

we find interesting stuff :

![](assets/3.png)

**joke def not netlogon :D**

we connect to profiles wich seels unusual and we have permission to do so:

![](assets/4.png)

Find multiple files, we got the juicy `.ssh` ready to be explored

![](assets/9.png)

we can get `id_rsa` but not `authorized_keys`

using `id_rsa` with the right premissions we got access to the machine :

![](assets/6.png)

And simply this is **SMB** in a _cybersecurity_ perspective :)
