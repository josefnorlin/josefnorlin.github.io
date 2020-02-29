---
layout: post
title:  "Make Windows Work Like a Mac"
date:   2020-03-25 13:00:00 +0200
categories: tech
image:  2020-03-25-make-windows-work-like-a-mac.png
comments: true
---
Disclaimer, I'm a developer and not talking about gaming here, and from that perspective, Macs are not as great as they used to be. I argue that Macs have mostly stayed the same while PCs have started to get their stuff together. Microsoft stopped its hit or miss releases (Windows XP = hit, Windows Vista = miss, Windows 7 = hit etc.) and started incrementally update Windows 10 together with it's partners until touch screen and pen features started to make sense, Windows Hello logs you in automatically, a unified settings app and even security, and updates are getting decent. That combined with cheaper price and unlimited customization and upgradability make Windows PCs look interesting again.

In my experience, Hackintosh is a little too time consuming and Linux isn't supported by Adobe and its Creative Suite. That is why I present you with this guide to set up keybindings, console, copy-and-paste etc to make the switch easier.

## 1. Set Up Windows Subsystem for Linux 2
One of the big things I've learned to appreciate with Macs is the Unix terminal. Now, you have that alternative for your Windows PC as well. 

Watch the ad: [Samsung Breaking-Out ad](https://www.youtube.com/watch?v=uoBh24itPeM)

![iPhone XS vs Samsung S9](/images/2018-10-12-iphone-xs-vs-samsung-s9.png)

> iPhone Xs and Samsung S9 comparison

## 2. Install Your Linux-flavour
Apple isn't leading the mobile phone development anymore. Look at the video ad below for examples of that. One of the latest feature Samsung beat Apple on is to use the phone as a desktop computer. All you need is an adapter, mouse, keyboard and screen and you're up and running. You might say, well, Apple doesn't lead but when they release a new feature they do a great job. Only problem is, Samsung and many others do a great job too. And often even surpassing Apple. Yes, iCloud, I'm looking at you.

Other innovations Samsung beaten Apple to: [Samsung Galaxy - Growing Up](https://youtu.be/R59TevgzN3k)

![Samsung DEX](/images/2018-10-12-samsung-dex.png)

> Interested? Take a look here: [Samsung - Desktop EXperience (DEX)](https://www.youtube.com/watch?v=G_Zdq0AjhXo)


## 3. Use Windows Terminal with Oh My Zsh
In Sweden by 30th of September 2018 an iPhone XS with 64 GB costs 12'489 SEK ($1'405), Samsung S9 with 64 GB costs 6'090 SEK ($685). So basically half the money. If the iPhone would be superior I would get it but I'm arguing its the opposite. I would say it's twice the price for an inferior phone. The Samsung S9 even comes with a memory card reader making its storage expandable. The day you need more space you can add it, not spending an extra 3'000 SEK upfront to get 192 GB more. 200 GB extra for a Samsung S9 would cost under 400 SEK. Not only is that close to 1/10 of the price, you can reuse your MicroSD card in your next phone/camera too.

![iPhone XS vs Samsung S9 price comparisson](/images/2018-10-12-iphone-vs-galaxy-price.png)

>1 & 2) As reported by Prisjakt 2018-09-30. See today's [iPhone XS prices here](https://www.prisjakt.nu/produkt.php?p=4652628), and today's [Samsung S9 prices here](https://www.prisjakt.nu/produkt.php?p=4919780).

## 4. Get your SSH-Keys Working
On windows 10, starting with version 1709 (win+R and type winver to find the build number), Microsoft is releasing a beta of the OpenSSH client and server. To be able to create a key, you'll need to install the OpenSSH server. To do this follow these steps:

    open the start menu
    Type "optional feature"
    select "Add an optional feature"
    Click "Add a feature"
    Install "Open SSH Client"
    Restart the computer

Now you can open a prompt and ssh-keygen and the client will be recognized by windows. 



## 4. Set up your VS Code
Ever tried to open an iPhone X(S/R) with part of your face covered by your pillow? Or while sneak-peaking at it from an angle? Face-ID is a great marketing tool but truth be told there are better ways to unlock your phone. Samsung has Face-ID technologies too but also includes a fingerprint reader on the back which I found far superior. While lifting my phone I can activate it just by holding it and the phone unlocks even before my eyes reach it making the otherwise mandatory "selfie look" at the iPhone X unnecessary. Just count how many times you unlock your phone everyday and count the extra seconds it costs you. iPhones doesn't present your apps directly either but shows you your "lock screen"-unlocked which makes even more seconds tick.

![Samsung S9 fingerprint reader](/images/2018-10-12-samsung-fingerprint.png)

> Samsung's fingerprint reader is located at the back, handy for your pinky while grabbing your phone

## 5. Customize your Keybindings to match your Mac
AHK + Wox + Copy and paste + ditto

![Apple's dongles](/images/2018-10-12-iphone-dongles.png)

> Want to charge and listen to music? Or just listening on your Bluetooth headset that just ran out on juice. No problem, just bring one or two adapters to your iPhone.

## To conclude...
If you're happy with your iPhone and want a smooth transition to something "old-new" go ahead get a new one. My only aim is to make everyone aware that things have changed over the recent years. Even if it's some hassle switching, the experience replacing my iPhone with a Samsung Android was like switching from my old SonyEricsson to my first iPhone 3G back in the day. You may need to move some contacts to your Gmail-account and install the apps you use again and setting them up, but if you're up for it's worth the challenge.
