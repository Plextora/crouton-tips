Crouton Tips      


*   [Website Source Code](https://github.com/Plextora/crouton-tips)
*   [My Games](https://plextora.itch.io)
*   [My Website](https://plextora.github.io/Web-Page/)

Important Links:

[Crouton README.md](https://github.com/dnschneid/crouton#readme)

[Crouton Download](https://goo.gl/fd3zc) 
------------
Crouton Tips
------------

**Tips for the software Crouton that allows Chromium OS users to use full linux desktops like XFCE or KDE**

**Keep in mind that this website is still being worked on!**
============================================================

-------------------------------------------------------------------------------
If you encounter any grammatical errors or website bugs please report it on the
-------------------------------------------------------------------------------

---------------------------------------------
**[GitHub Issues Page!](https://github.com/Plextora/crouton-tips/issues)**
---------------------------------------------

----------------------------------------------------------------
**Synchronized clipboard with Chromium OS and Crouton on Xorg!**
----------------------------------------------------------------

If you're like me and love the benefit of a shared clipboard with Chrome OS and Crouton, Then you'll love the extension target! It syncs the Chrome OS and Crouton clipboards without lost performace from the window the xiwi target provides. But you'll need the [crouton extension.](https://chrome.google.com/webstore/detail/crouton-integration/gcpneefbbnfalgjniomfjknbcgkbijom) This is how you would use it while installing a chroot:

    sudo crouton -n happiness -r focal -t extension,xfce

---------------------------------------------------------------------
**What's the most lightweight DE (Desktop Environment) for Crouton?**
---------------------------------------------------------------------

In my opinion, the most lightweight DE that Crouton has available is the [Enlightenment DE.](https://www.enlightenment.org) It's only 50mb, and it runs fast. But sadly, in my testing it only worked with Ubuntu Xenial, which is slowly becoming more and more out of date.

--------------------------------
**How to install Bionic Beaver**
--------------------------------

If you try installing Bionic Beaver normally like this:

    sudo crouton -r bionic -t xfce

you'll run into errors before you even get to create a new user. And you can't rerun the script. You have to delete the chroot and start all over again. The reason why the errors occurs seems to be becasue the package **xserver-xorg-video-all** never gets installed. So in order to fix this error, we'll need to install the barebones of a chroot:

    sudo crouton -r bionic -t core,audio,cli-extra

This will install a base linux system with CLI. Then after creating a user, do this command:

    sudo enter-chroot

and then this one:

    sudo apt-get install xterm xinit

which will install the **xserver-xorg-video-all** package. Now, finish your setup with something like:

    sudo crouton -n bionic -t x11,xorg,extension,keyboard,xfce -u

And now you have a Bionic Beaver chroot!

-------------------------------------------------------------------------------
**Tired of the annoying crosh window in the background? Here's how to fix it!**
-------------------------------------------------------------------------------

If it's your pet peeve that the crosh window is always running while you're on Crouton, there's a easy fix for it!

All you have to do is boot into your chroot like this:

    sudo startxfce4 -b

And now your chroot will open and you can go back to Chrome OS and exit crosh!

------------------------------------------
**How to fix audio not working in Crouton**
-------------------------------------------

If audio in Crouton isn't working for you, there is a very handy fix for this. And in my experience I have to use this command every time start up my chroot to get audio working. To fix this, start up your chroot. Go into the terminal, And type in this command:

    pulseaudio --start

Now, you should here some audio!

### [Here's a audio test for you to make sure it's working!](https://www.youtube.com/watch?v=pSVoqmugJVM)

------------------------------------------
**How to reduce load from ChromeOS Chrome**
-------------------------------------------

ChromeOS runs alot of Chrome processes. If you primarily use your chroot, use the -b command whenever you boot Crouton, and find Crouton very sluggish, this might be the fix for you! It kills alot of Chrome processes without breaking anything,

#### **But any unsaved work will be lost!**

Just copy paste the command below into your Linux Terminal.

    ps ax -o sess,pgrp,pid,cmd | awk '$4 ~ /\\/chrome$/ { print $3 }' | xargs $nodo kill

Currently on Chrome OS version 92, if you switch back to Chrome OS your Chromebook might freeze and open Chrome back open again, if this happens and you want them killed again just simply switch back to Crouton and run the command listed above again.

------------------------------------------
**How to control audio volume in Crouton**
------------------------------------------

If you don't want to switch back to Chrome OS every time you want to turn up/down the volume, there's a fix for this!

Crouton has a way to turn up/down the volume within your chroot without having to always switch to Chrome OS, and it affects Chrome OS as well so audio is synced between the two! All you have to do is go into your Linux terminal and copy paste this in:

    alsamixer

Then, you'll get a gui with a big vertical volume bar. You can use number keys 1-9 to quickly jump volume values (for example, pressing 1 goes to 10, 5 goes to 50, etc.) or you can use the arrow keys to go to more precise values. I recommend to keep the terminal open for quick volume changes. If you decide to keep your volume and not have it open, just simply close the terminal.
------------------------------------
**Avoid data corruption and turn off sleep mode!**
ChromeOS by default has sleep mode turn on when you are inactive on your Chromebook. This feature actually still applies to Crouton and it could cause some problems, including data loss. So, in order to turn off sleep mode for ChromeOS and Crouton, go into ChromeOS settings, search "Sleep", and then click the first result. Set both options to "Keep display on" or "Turn off display". Just don't have it on the sleep option. And after that, it's done! No commands or anything for this tip!
------------------------------------
**How to safely shut down chroots!**
------------------------------------

If you're done with what you're doing in your chroot or Chromebook, it's important to know how to safely shut down the chroot without damaging the operating system. I learnt this the hard way when I forcefully shut down ChromeOS with the chroot still open and had to use a recovery image to save my Chromebook! In order to cleanly shut down the chroot, log out of the desktop environment you're in. **DONT PRESS SHUT DOWN!!** It should take you back to crosh and show progress of it shutting down the chroot. If you used -b while booting your chroot, I advise at least waiting 1-2 minutes depending on your Chromebook's speed. And then after that, you can shut down ChromeOS if you want to without doing any damage to the system!

[⬆️ Back to top ⬆️](https://github.com/Plextora/crouton-tips#readme)


# More tips coming soon!

This website/repo is created and mantained by [Plextora](https://github.com/Plextora)
