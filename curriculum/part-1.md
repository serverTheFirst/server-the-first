# part-1


It may seem elementary to start at the very beginning, but very few people havy any level of understanding of how the internet works and how computers communicate with each other. This essay will cover items 1-3 on the manifesto, namely the b asics of network communications. Here are a few keywords that will be important through this entire exercise:

LAN - Local Area Network - This is the network that is inside of your home or business, on your side of the router. Moving forward we may refer to this just as the network.

WAN - Wide Area Network - your LAN may be able to reach out to the internet (WAN) or it may not. There are valid reasons for both cases, but connecting your router to the WAN (internet) will generaly give devices on your network access to the internet.

Gateway (router) - Keep in mind that router is a colloquial term used when talking about stuff, but in most applications it is described as the gateway. This is where the (optional) WAN and LAN meet. The router is the single point where outbound and in bound internet traffic occurs. It stands inside of the cable modem, but the outermost point of your LAN.

Switch - A device that connects to your network to allow more devices to be plugged in. It can sometimes be referred to as a hub. You run one wire to the router and then plug everything into the switch. They get more complicated than this, but for now that's all you need to know.

DHCP - The part of the router that assigns an ip address to a device when it connects to the network.

Device - anything that connects to the LAN.

IP Address - the location on the network a device exists.

Port - A more specific location than ip address. usually written as IPADDRESS:PORT

DNS - How names (www.google.com) gets translated into IP addresses (8.8.8.8)



Before we discuss any of the complexities of networking, we need to first understand how networks are organized and how devices communicate. The main way networks identify devices both WAN and LAN is by IP address. There are some videos I will link desrcibing them in more detail, but for know think of it as less of an address and more of a phone number. They are 4 sets of numbers separated by dots 192.168.1.1, for example.

Since there are a whole bunch of homes/businesses in the world with internet access, each of them needs a phone number. If google (8.8.8.8) wanted to call the website up of facebook, they would be accessing 66.220.144.0. The ISP is the one that determines the IP address of your home, just like the telecom company picks your number.

Network IP addressing inside a LAN is a bit more straightforward. For reasons similar to why we don't have 911 as an area code in America (or 912 if you know whats up) we can't have inside ip addresses work like outside addresses otherwise there would be massive ip conflicts. Imagine 4 places across the world with the exact same phone number. For this reason, some ip address blocks have been reserved for building LAN access. There are names and explanations about all of this online, but the basic jist of it is that you essentially have two choices when building your home network.

192.168.1.XXX - This is the standard ip address schema of every home router available. This is generally considered an ip schema for homes and small businesses. The complicated reason this is for homes and not businesses is there are fewer locations allocated than the enterprise IP addressing.

10.X.X.X - it works the same way as 192. Ip addresses, its jsut that there are way more locations availble. Each digit location in between the dots has 254 places, so 10.(up to 254).(up to 254).(up to 254).(up to 254).

Because a typical home network wont have hundreds or thousands of devices connected to it, keeping the default to 192. is just fine and you wont need to change a thing at setup. All of these settings are configured in your router and for the most part, all you need to change on the router is the admin credentials.

Here is a super basic map of what a home newtowk could look like:

WAN IP - 8.8.8.8
192.168.1.1 - Gateway (the router always has the .1 position)
192.168.1.5 - server
192.168.1.88 - xbox
192.168.1.33 - laptop

As you can see all of these devices are on the same LAN. We know this because the 192.168.1 part of the ip address is identical. The number that is different, lets jsut for now call it the extension. The server is located at 192.168.extension5.

Let's talk about the server a bit. A server has a bunch of apps installed on it that run services and stuff for you. Most of these apps are available to manage through the browser. The reason it is this way, is that you don't normally work on a derver with your mouse and keyboard connected directly to it. Rather, the server sits on the network and is accessed throuh it so if you type in 192.268.1.5 you will get the management console for the server. To get to the app on the server we need to know which port it is assigned to. This is easy and will be discussed later, but it is important. Let's say we want to acces sone of our server applications. We know the IP and we know the port so we van type in 192.168.1.5:4444 and the browser will request that the server discplay whatever is connected to that port. Now you are accessing that app using the browser of your device.

OK, so we understand ip addressing because we know how phone numbers work. We understand that a website is just words (www.) that get translated to the IP address (DNS) of the site. Now let's do some examples of inbound and outbound traffic.

Example 1 - You want to know what time the cricket match is. Now you've never watched cricket before, and you cerainly haven't spent any time on your computer searching for cricket teams, so there is no search history or anything like that on your computer. You hop on to your browser and go to www.whatthehelliscricket.com. At this point the browser on your device asks your router to go to the website you just typed in the search bar. It asks the router if it knows the IP address www.whatthehelliscricket.com. Since you have never visited that website, your router doesnt know, so it goes to a secondary (usually 3rd party by default) "phone book" (DNS server), that is often times google. So essentially you are asking your friend for a phone number and if your friend doesn't know, they ask the principal and now everyone knows you know nothing about cricket and your whole life is a lie. it gets a lot scarier if you have to visit www.iwasraped.com or www.abortionprovider.com or www.myparentshatemebecauseimgayortrans.com. Thankfully, its pretty easy to set it up so that the friend calls the website directly and asks for its number. That's called a recursive DNS and you will learn how to set that up in less than an hour.

Example 2 - You are at a bar chillin with your homies and you HAVE to brag about how cool your server is and how you left google and now you're ready to talk about it like you're a vegan or a crossfitter. So you grab your phone and browse to www.webapp.yourcustomdomain.com and BAM - you can now use that web ap from your phone. The app could be your security camera program (shinobi), your media server to watch movies (plex), or your custom code server environment so you can work securely. Almost every app installed on your server will be able to be accessed remotely.

OK - now you have typed your cool url into your browser and you are about to visit your personal website. You're connected to the bar's wifi. Now your phone asks the bar's router where to go, and then it probably asks google where for DNS resolution. Because your url is setup to direct to a particular ip address (your home) and port (your web app) the router checks its settings and  determines whether or not to let you in. Thankfully we can configure your setup so you are always connected to your network and you never have to rely on the bar's or googles prying eyes.

There you go. That is the 1st grade level understanding of how computers vommunicate with each otehr over WAN and LAN. Any network pro might be screaming at the simplification of this, but for home networkers just trying to get started, this is a solid foundation to learn from.
