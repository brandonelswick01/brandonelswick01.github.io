---
layout: post
title: "Switching to Linux | Entry 3"
date: 2026-05-10
---

# Overview
In this article I will be talking about Linux, specifically my switch from Windows a few years ago and why I chose to migrate to the kernel rather than stay with Microsoft's Operationg System.

## Inroduction

### Linux isn't an OS, it is a kernel
When most individuals hear the word "Linux" they think - "what the hell is that?" They don't realized linux runs a majority of the world's applications. You might think to yourself - "I have never and/or will never use Linux a day in my life!", that is where you are wrong. Ar you an android user? Do you own a smart TV? Have you ever connected to a Minecraft Server to play with your friends? If you said to any of this then you have used Linux and you have enjoyed it.

#### Why is Linux a kernel and not an OS?

Linux is often considered an OS when new users talk about it. Because it acts as an OS. The term "kernel" I am using to describe the nature of the technology is technically true.

Linux lacks the features of a GUI(Graphical User Interface), manage files, or even run apps. The kernel is used for: CPU, Memory, and peripheral devices.

#### How is the Operating System built?
A Linux Operating System is built by combining: the Linux kernel, GNU Libraries(a majority of the time), System Utilities, the Init System, and a bootloader.

The kernel is only a small aspect of what goes into your favorite distributions like: Ubuntu, Mint, Fedora, Arch, and Debain just to name a few. There are over 600 different distros, a few named above. Each distro is made for something, made to be something. We'll get into that now.

#### Different Types of Linux Distributions

##### User Friendly Distributions to make the switch
+ Ubuntu
+ Linux Mint
+ Pop!_OS
+ ZorinOS

These distributions were created to bring people over to the...wait for it..."dark side". At least that's what people think when you tell them you are a Linux user.

The distros I mentioned previously above are designed to be UI/UX friendly. You don't have to run terminal based commands to move and/or copy and paste files, to open, or to remove. It's as simple as using right-click on mouse and clicking "delete".

##### Linux Distributions used for InfoSec

+ Kali
+ ParrotOS
+ BlackArch
+ AthenaOS
+ RedHat
+ CSI Linux
+ SELinux

These distributions listed above are used for various purposes such as: PenTesting, Digital Forensics & Incident Response, and Security.

## My Journey with the kernel

### What OS did I choose when I made the switch?

I ultimately chose Ubuntu as my switch. I know it's pretty basic, everyone chooses it. It took me roughly three months to understand the fundamentals of using the command-line. It isn't too much. It was just so overwhelming because I had no idea where to start. So I decided to use the cheatsheet. It helped it a lot. Just start by using:

+ pwd
+ ls
+ cd
+ grep
+ systemctl

### What did I "Distro Hop" to next?

I then hopped to Mint. Mint was a little bit weirder than I expected. I mean it's just a fork of Ubuntu. I was still using Debian-based Systems. I got very familiar with it, it was exciting. Just the curiousity, I mean I learnt something more better every day.

My next distro was Fedora. Fedora was a little different. I went for using "apt" to using "dpkg" to install things but it was similar and familiar. Then I went from Fedora to Arch. That's where I settled. Arch gave me that DIY-Lean system. I only need to install exactly what I need. I've been hooked since. On my personal devices I have not used windows since.

Now I do use Ubuntu on the server-side a lot. Most of my homelab is running ubuntu because of how stable it is.

I think you should give it a try, I mean what is the worst possible thing? I can even show you how to do it! You don't need to wipe Windows off your main rig to get started.

## How to set up a Virtual Machine

In this section I will be discussing how to set up a VM and download your first ISO.

### What software do you need?

You'll want to download Oracle VirtualBox, just follow the installer. Then you'll need to head over to one of these three sites to download your ISO. It might take some time to download - get some coffee.

+ [Ubuntu](https://ubuntu.com/download/desktop "Ubuntu")
+ [Mint](https://linuxmint.com/download.php)
+ [Pop!_OS](https://system76.com/pop/download/)

### How do I make a Linux VM?

We'll get into that now! I don't think I will be able to explain it as good as the [documentation](https://www.virtualbox.org/manual/topics/create-vm.html) itself could. Now just install as you would for a Windows Installation!
