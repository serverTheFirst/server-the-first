# journey-notes


1. **Server Build Process** - this wasn't so bad. Between pcpartpicker and my buddy's direction all the parts were compatible and fit together easily. #protip get some extra standoffs when you get your mother board and case. There may not be enough standoffs to fully secure your motherboard to the case. Place the motherboard on the case and make absolutely certain every post hole on the board has a standoff underneath it. There isn't much else to building a pc and other videos and sources will be able to explain that process much better.

2. **Installing unRAID** - again fairly easy. There are lots of videos on how to get the usb drive from unRAID. If you built your server and got it to POST, then installing unRAID is something as simple as changing a few settings int he bios.

3. **Evaluating Software** - this is the one that makes my head spin. There are so many offerings for every single solution it is really overwhelming. If you are truly trying to make a go at learning this valuable skillset you have to think about software as more than software. Most users interact with the very tip of what software can do and rarely use the deeper customization features that software offers. It is best to evaluate each software solution you need before you implement one.

The first piece of software I evaluated was my [web-browser] of choice. I had been mostly a safari user, but my browser choice never mattered because I only used it for basic browsing. This becomes very different as your server grows. Most of the services are accessed via web browser, and being comfortable with your web browser speeds up the time it takes to navigate. #protip You will need some solution for bookmarks. Don't worry about installing the cool shiny start pages right now. Adding the bookmarks to your browser or browser extension will start to give you a feel for the deeper UI of the browser. 

Some questions to ask yourself:
- does the ui feel natural
- are the things I need to access easily accessible
- does the browser have integrations with APPNAME
- does it work in all the places I need it to work (mobile, pc, mac, linux)

I personally chose [[vivaldi]] browser. It has a ton of customizability, including the most innovative tab management systems I have seen. I played around with the customization options quite a bit and I feel like I haven't even scratched the service. 

The next piece of software you will want to get comfortable with is your [text-editor]. This is where you will do a lot of the file editing you may want to do. It is also possible to edit files using the command line, and there are times when that is much easier, but for now (and for most cases) using a text editor is going to be the first way you edit files. Choices abound in this space, and I highly recommend you play around with a few. 

I tried sublime text, atom, and [[vscode]]. I ended up using vs code because that is more or less what every content maker in this space uses. [[codeserver]] is just a containerized version of vs code. #protip Install vs code on every device you'll use to access your server, *and* install the containerized version on your server(s). This ensures you have all of the access points you can to work on your system.

The third software I needed to evaluate is a [[password manager]]. Sure apple/google/ms all have password management systems baked into their systems, but that route still relies on large corporations hosting your data. There are many many many password managers to look at. This hobby/lifestyle will end up leaving you with database users/passwords, services users/passwords, device users/passwords, and more - and the thing that complicates this is that they are all (for the most part) the same ip address, so naming the login [nextclouddbadmin] instead of 10.13.10.45:5424 clears things up. Most content makers and community users rely on [[vaultwarden]] to manage their passwords, and so do I.

TODO email
TOTO task manager

4. **Securing the network** - This really needed. It is not enough to hide your services behind a reverse proxy (more on that later) and leave it at that. Once you decide to host your own data and leave the cloud, ensuring that your network is secure is very important. I elected to go with a #unifi USG at both my home and work locations. One of the features of this hardware is that you can setup a VPN tunnel between each USG and then the entire network is accessible.

#protip
-strong username and password on your router
-port forwarding (more on this later)
-TODO network hardening

5. **Installing Containers** - the process of installing docker containers differs heavily from program to program. I have separated the containers into packages that group similar apps for easy comprehension. Each container installed on the server has it's own notes on install and best practices and a dummy sheet with the basic details.

6. **Sprint before crawl** - this is a big deal for anyone coming into this hobby and following my guide: you have no idea what you don't (and won't) know how to do. Even if you follow the guides here there will be mountains and mountains of reading if you want to go beyond what this server can do for you. 




