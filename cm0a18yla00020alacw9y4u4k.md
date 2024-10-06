---
title: "Steps to Resolve Ubuntu OS Boot Failures and Boost Disk Space Using GParted"
seoTitle: "Fix Ubuntu Boot Issues & Increase Disk Space"
seoDescription: "Resolve Ubuntu boot failures and expand disk space using GParted with this step-by-step guide. Ideal for both Linux newbies and seasoned users"
datePublished: Sun Aug 25 2024 20:39:29 GMT+0000 (Coordinated Universal Time)
cuid: cm0a18yla00020alacw9y4u4k
slug: steps-to-resolve-ubuntu-os-boot-failures-and-boost-disk-space-using-gparted
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/4Mw7nkQDByk/upload/8b8614cb5edd2c01790e98730fec8ebd.jpeg
tags: ubuntu, linux, technology, terminal, ubuntu-2204

---

Have you ever encountered a heart-stopping moment when your Ubuntu OSrefuses to boot? Recently, I faced this exact scenario with my Ubuntu 22.04 installation. In this blog post, I'll walk you through how I resolved the boot issue and expanded my disk space using GParted. Whether you're a Linux newbie or a seasoned user, this guide will help you navigate similar challenges.

# The Boot Problem

One morning, my Ubuntu 22.04 OS greeted me with a black screen and a cryptic message:

```bash
/dev/sda4: clean xxxxxx/xxxxx files, xxxxxxxx/xxxxxx blocks
```

### Step 1: Booting in Recovery Mode

To troubleshoot, I booted Ubuntu in recovery mode.

Here's how:

1. Restart your computer.
    
2. Press and hold Shift during boot to access the GRUB menu.
    
3. Select "Advanced options for Ubuntu."
    
4. Choose a recovery mode option.
    

In recovery mode, I cleared the cache, which allowed the system to boot normally.

### Step 2: Addressing Low Disk Space

After booting, I received another warning:

```arduino
"Low Disk Space on "Filesystem root"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724616984198/f53fbc34-05bd-4546-b513-879521f08db5.png align="center")

To investigate, I ran this command in the terminal:

```bash
df -h
```

This confirmed that /dev/sda4 was 100% full.

### Step 3: Analyzing Disk Usage

I used the Disk Analyzer tool (also known as Baobab) to check my disk usage. However, all the files seemed important, so deleting them wasn't an option.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724617147576/4ab7117f-379a-4011-9bf8-0ea9748b57f1.webp align="center")

### Enter GParted: The Disk Partition Savior

What is GParted? GParted (GNOME Partition Editor) is a free, open-source partition editor for managing your disk partitions graphically. It's a powerful tool that lets you resize, copy, and move partitions without losing data.

Key features of GParted:

* Resize, create, and delete partitions
    
* Move partitions
    
* Check and repair file systems
    
* Set partition flags
    

How to Use GParted to Expand Disk Space:

1. Create a bootable Ubuntu USB drive:
    
    * Download the Ubuntu ISO from [ubuntu.com](https://ubuntu.com/download/desktop)
        
    * Use a tool like [Etcher](https://etcher.balena.io/#download-etcher) to create a bootable USB
        
2. Boot from the USB drive:
    
    * Restart your computer
        
    * Enter BIOS/UEFI settings (usually by pressing F2, F12, or Del during boot)
        
    * Set USB as the first boot device
        
3. Choose "Try Ubuntu" from the boot menu
    
4. Install GParted: Open a terminal and run:
    

1. ```bash
    sudo apt-get update
    sudo apt-get install gparted
    ```
    
2. Launch GParted:
    
    ```bash
    sudo gparted
    ```
    
3. Resize partitions:
    
    * Select the partition you want to shrink
        
    * Right-click and choose "Resize/Move"
        
    * Adjust the size, leaving unallocated space
        
    * Apply the changes
        
    * Select your root partition (/dev/sda4 in this case)
        
    * Resize it to use the unallocated space
        
    * Apply changes
        

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724617672214/a8ad9c9f-83b2-4d77-9ac1-316203ba119f.png align="center")

7. Reboot your system
    

### **Conclusion**

By using GParted, I was able to expand my root partition and resolve the low disk space issue. Remember to always back up your important data before making changes to disk partitions.

Have you ever used GParted or faced similar Ubuntu issues? Share your experiences in the comments below!

> [The Linux philosophy is 'Laugh in the face of danger'. Oops. Wrong One. 'Do it yourself'. Yes, that's it.](https://www.brainyquote.com/quotes/linus_torvalds_163637)
> 
> [Linus Torvalds](https://www.brainyquote.com/authors/linus-torvalds-quotes)