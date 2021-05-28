# Crouton Tips   

*   [My GitHub](https://github.com/Plextora)
*   [My Games](https://plextora.itch.io)

[Crouton Download](https://goo.gl/fd3zc)

[Crouton README](https://github.com/dnschneid/crouton#readme)

[Website Source Code](https://github.com/Plextora/crouton-tips)

[README Source Code](https://github.com/Plextora/crouton-tips/blob/master/README.md)

Crouton Tips
------------
https://github.com/Plextora/crouton-tips
**Tips for the software Crouton that allows Chromium OS users to use full linux desktops like XFCE or KDE**

**Keep in mind that this README is still being worked on!**
============================================================

If you encounter any grammatical errors or bugs on the website or README please report it on the
-------------------------------------------------------------------------------

**[GitHub Issues Page!](https://github.com/Plextora/crouton-tips/issues)**
---------------------------------------------

**Synchronized clipboard with Chromium OS and Crouton on Xorg!**
----------------------------------------------------------------

If you're like me and love the benefit of a shared clipboard with Chrome OS and Crouton, Then you'll love the extension target! It syncs the Chrome OS and Crouton clipboards without lost performace from the window the xiwi target provides. But you'll need the [crouton extension.](https://chrome.google.com/webstore/detail/crouton-integration/gcpneefbbnfalgjniomfjknbcgkbijom) This is how you would use it while installing a chroot:

    sudo crouton -n happiness -r focal -t extension,xfce

**What's the most lightweight DE (Desktop Environment) for Crouton?**
---------------------------------------------------------------------

In my opinion, the most lightweight DE that Crouton has available is the [Enlightenment DE.](https://www.enlightenment.org) It's only 50mb, and it runs fast. But sadly, in my testing it only worked with Ubuntu Xenial, which is slowly becoming more and more out of date.

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

**Tired of the annoying crosh window in the background? Here's how to fix it!**
-------------------------------------------------------------------------------

If it's your pet peeve that the crosh window is always running while you're on Crouton, there's a easy fix for it!

All you have to do is boot into your chroot like this:

    sudo startxfce4 -b

And now your chroot will open and you can go back to Chrome OS and exit crosh!

[⮝ Back to top ⮝](https://github.com/Plextora/crouton-tips#readme)

**More tips coming soon!**
==========================

This website/repo is created and mantained by [Plextora](https://github.com/Plextora)
