# part-2


Now that we have some foundation to work from, it's time to start thinking about what your system will do. Most of you at this point are pretty overwhelmed by trying to design things that you dont understand yet, but that's ok. These essays are more or less designed to teach you what you need to know when you need to know it. If something doesnt make sense, just keep reading because a lot gets explained as you go.

The first thing you want to decide before anything is the ip schema you want to use. Lets just say you decded to keep the default router address of 192.168.1.1. That was easy.

Next, in your router settings you will want to reserve some IP addresses so not all of them get assigned to devices that hop on the network. Usually you want a pool of 20 or so ip addresses that are available only manually. So we will need to reserve those in settings.

You will want to think about the devices that are always on the internet and determine whether to give them a static ip (every time that device connects it uses the same ip address) or whether to allow the DHCP server on the router to assign the ip from the available ip addresses. Here are a few items that should absolutely be set to static ip (you can use different suffixes for anything except the router, this is just a list):

Router - 192.168.1.1
PiHole (recursive dns) - .2
Server - .3
Printer - .4
Home computer - .5
Personal Laptop - .6
Security Cameras .7 .8
Access Points - .9 .10


All of these items get assigned static ip addresses because it is advantageous to know where they are at all times. You will absolutely need to pop into your server, and if the ip changes every time it restarts you'll have to hunt for it. Same goes for all the other computer devices.

Here are some devices you can just let connect and have DHCP assign ip addresses. These are essentially devices that are on and off a lot and you won't need to access them directly via ip address.

Guest devices
Game consoles
cell phones
streaming devices
