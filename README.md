# Lab 2 Go

is a live-build config and tree to build a BunsenLab*ish* live image
on a debian system made for use with encrypted persistence.
I added some forensik tools (testdisk, magicrescue etc.. ) and the [kali-anonsurf package](https://github.com/Und3rf10w/kali-anonsurf) for surfing under the hood while away from home. 

## Usage

Install the live-build package and some essentials.

`sudo apt install -y curl git live-build cdebootstrap`

Clone this repository wherever you may like... 
\* *Note that the caching done while bootstraping the system may need a considerable amount of disk space*

`git clone https://github.com/Naik-NLZ/lab2go.git`

`cd lab2go`

... and build the image.

`sudo lb build --verbose`

The configs are already included.

This may take some time (could definitly be improved!) and may or may not fail at any stage due to changed repositories or singing keys.
Also, you are highly encouraged to have look through the files in **./config/package-lists/** (and all the rest) and change them to your liking before building the image.
Please also note that there is a file called **./config/includes.chroot/etc/live/user.conf** which is meant to change the name of the default user and hostname in livesession. The default password will stay **"live"** no matter to what you change the values in this file. The default hostname (lab2go) is also specified in the kernel parameters provided by various isolinux files so you might need to change the there too.


You should then be able to create a live medium by means of a DVD-burner, a propper aplication like [Etcher](https://www.balena.io/etcher/) or **dd**
and set up (encrypted) persistence like descriped in the [Kali docs](https://www.kali.org/docs/usb/dojo-kali-linux-usb-persistence-encryption/)

If you decide to copy the content of the iso file to an existing partition of your thumbdrive, you will probably need to rename all files and folder containing **isolinux** to **syslinux** and install syslinux/extlinux manually afterwards for the media to boot. 


## Thanks to

All this is put together with the help of 
 - [the Debian Live Manual](https://live-team.pages.debian.net/live-manual/html/live-manual/toc.en.html)
 - [the Kali Linux Documentation](https://www.kali.org/docs/)
 - and great work of the [BunsenLabs team](https://bunsenlabs.org)
 
Thank you all for your time and your effort!



