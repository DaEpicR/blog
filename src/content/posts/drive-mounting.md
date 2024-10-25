---
title: 'How to auto mount a drive in Linux'
description: 'Here is a simple way to mount any drive with any filesystem in Linux , using `fstab`'
pubDate: 'May 31 2024'
heroImage: 
  src: ''
  alt: ''
order: 1
tags: ["Guide", "Linux"]
---
![](/public/blog-placeholder-2.jpg)

To mount any drive with any File system (NTFS, BTRFS, etc...) using `fstab` (File System Table), you'll need to add an entry for the drive in the `/etc/fstab` file. Here's how you can do it:

1. Find the **UUID** (Universally Unique Identifier) of your in ex: *NTFS* drive. You can do this by running the following command in the terminal:

```bash
sudo blkid
```

Look for the entry corresponding to your NTFS drive. It will look something like this:

```bash
/dev/sdb1: UUID="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" TYPE="ntfs" PARTUUID="xxxxxxxx-xx"
```

Note down the UUID value.

2. Decide on a mount point for your NTFS drive. This can be any directory you choose. For example, `/mnt/ntfs`.

3. Now, open the `/etc/fstab` file in a text editor with root privileges. You can use `sudo` with a text editor of your choice. For example:

```bash
sudo nano /etc/fstab
```

4. Add a new line to the end of the file in the following format:

```bash
UUID=<UUID> /mnt/ntfs ntfs defaults 0 0
```

Replace `<UUID>` with the UUID you noted down earlier.

5. Save and close the file.

Now, your NTFS drive will be mounted automatically at boot to the specified mount point (`/mnt/ntfs` in this example) with default options (`defaults`) for read/write permissions.

Make sure the mount point directory (`/mnt/ntfs` in this case) exists before you reboot, or you can create it using:

```bash
sudo mkdir -p /mnt/ntfs
```