---
layout: post
author: rahimi
---

**I use Arch BTW!**

I have been a avid linux user since the late of 2019 due to my obsession with Mr. Robot and hacker wannabe cringey teenager. Long story short, I failed on my attemp to be a hacker **obviously**, and after distros later, I stick with Linux Mint.

The reason is 1) easy to setup and work out of the box 2) familiarity with Ubuntu make is easier to use.

I also happen to own several old laptops that have been collecting dust since I don't know when, and I think it just normal, **very normal** for me to use it to install linux distros of various flavour. Honestly, I just love to distro hop and play around with my system, the feeling when you installed it successfully on bare metal is very satisfying. I have tried some major distros including Debian, Fedora, Arch, and void --including their child.

The point is, I have spend countless hour installing and setup my freshly installed linux distro --the best part--I've repeat this cycle so many time, but I always go back to Linux Mint. But, this is not about my linux journey or how I really really love Linux Mint, this is about my transition from Linux Mint to Arch Linux (for a n times).

Here's the story, I've use Arch multiple times before and my setup is basically the same, Arch + i3. I really love tiling window and i3 happen to be the first one that I tried and I don't bother to change to other tiling window manager for whatever reasons (sway look fun), i3 just work for me and I really love the workflow (__For now__). But as I said before, I always go back to Linux Mint because it's really feel like home to me. There's a time when I used Arch for a month then I changed back to Linux Mint for no reason, that how I love Linux Mint.

But, I have this habit where I like to start fresh every time I start a new semester, new book, new pen/pencil, new OS etc. Yes I'm old but I'm still a student. So this time I think to myself, "let's try to use Arch for this whole semester", and the journey start on September 2023. 

The installation is quiet easy since I've done it so many times and I have some script for packages that needed to be install during installation and all. To be honest, the installation process is not so hard and everyone can do it if they can read the wiki properly, just remember to install network manager `networkmanager` and boot manager (I use `grub`) and you will be safe. It's very important to make sure you install grub instead of just download it. There're two separate command to download and install grub. To be fair, I have managed to forgot about this several time, it will be pain to chroot back and install it so usually I just start new installation.

The reason why I love Debian based distro and always going back to Linux Mint is because it's easier to find .deb packages. The packages that I have to installed no matter what is Visual Studio Code and Google Chrome for college, and pacman doesn't have them. So that's the main reason why I used Debian based distro before..... I know how to use AUR properly. Both Visual Studio Code and Google Chrome can be install using AUR and I used yay to manage my AUR. It get easier after you know what you want to do right ? 

The way I setup my system is by using alacritty as my main terminal emulator and I set it on my first workspace, second workspace is for browsers such as Firefox __For my personal browsing stuff__ and Google Chrome __For college stuff only__. Then I have Visual Studio Code run on workspace 3 and other software on other workspaces. 

This ensure my productivity and make it easier for me to do my work when I can switch workspaces like that, its like my brain have been wired with this setup. I also used tmux and neovim(__lazyvim) for coding personal project and editing text. It's not like I'm good at vim, I just love the keybinding especially vim movement. I also use vim extension on Visual Studio Code because I used to it. I try emacs and still use it sometime, there's this phase where I force myself to learn emacs until I get good with it, but I still need vim keybinding and movement because emacs movement is quite awkward for my fingers. It's not emacs fault tho, actually I really like it for customization and extension but I just love vim more. 

> "There's no need to fight which one is better and all, just use which one make you more comfortable, I learn vim first then emacs, so maybe that's the reason why vim is my choice, maybe I will use emacs if I learn it first, who know?"

For file manager, I use pcmanfm because it's really lightweight and set it to spawn at workspace 4. Actually, file manager and mount thinggy was also one of the reason why I changed distro back then, I used external hard disk a lot and I don't know how to automatically mount it, I have to `sudo mount /dev/blabla /mnt/blabla` every time and it can get very tired right?! I know I'm stupid, the only thing that I have to install is `gvfs` and it help to mount the drive automatically so my problem is solved.

Other software that I use is Okular for PDF viewer, this is very important for me since all my college's resources and book are in PDF so I choose Okular because it's easy to use. VLC for video and music player, actually I didn't listen to music much and I use Spotify whenever I want to listen to music. Thanks again for AUR. 

It's been almost a month since I use Arch and I hope that I can maintain and use it atleast until January which will be the end of this semester, then maybe I can change to other distro or back to my beloved Linux Mint. I also planned to keep updating about my journey with Arch Linux or....... my journey with other distro if I change to other distro.

For now, Arch is very good and I start to maintain it very well, the most important thing is it have all the software needed for my college. It will be pointless if it didn't support the software needed for my college.