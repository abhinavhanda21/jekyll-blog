---
layout: post
title: A Whole-Network Ad Blocker, or a Call-Home VPN
date: 2017-09-05 18:36
author: abhinavhanda
comments: true
categories: [Uncategorized]
---
<h3>What You’ll Need</h3>
<ul>
	<li>Raspberry Pi (any model)</li>
	<li>SD card and a card reader</li>
	<li>Power supply</li>
	<li>Ethernet cable</li>
	<li>Keyboard (for initial setup)</li>
</ul>
<h3>Step One: Download and Burn the Pi-Hole Image</h3>
The first thing you’ll need to do is download and burn the Pi-Hole image. The image is a version of a Raspberry Pi operating system called <a href="https://www.raspberrypi.org/forums/viewtopic.php?f=63&amp;t=100976" target="_blank" rel="noopener"><strong>Diet Pi</strong></a>, which cuts a lot of junk from Raspbian, and is packed with all the software needed to run the ad blocker.
<h3>Step Two: Boot Up and Configure Your Raspberry Pi</h3>
Insert your SD card into your Raspberry Pi and connect the keyboard. Connect the Ethernet cable to your Wi-Fi router, then plug in your Raspberry Pi, and wait for it boot.
<div class="js_ad-mobile-dynamic js_ad-dynamic ad-mobile-dynamic"></div>
When you first boot up your Raspberry Pi, it’ll boot and reboot several times. This is normal, so let it happen. For the most part, it’s doing basic setup procedures like expanding the file system and getting the network settings configured. Eventually it will boot up to a login screen.

Log in with the <strong>username:</strong> <em>root</em> and <strong>password:</strong> <em>dietpi</em>. Once you do so, your Raspberry Pi will check for and possibly download a set of updates, so wait this out as well. When it’s done, you’ll need to reboot again, then login.
<h3>Step Three: Set Up a Static IP Address for Your Pi</h3>
After all those reboots, you’ll eventually get to the DietPi Setup screen where you can assign a static IP address. This is necessary so your Pi will always be available at the same address from any of your devices. Here’s what you’ll need to do:
<ol>
	<li>Select Okay at the initial setup screen.</li>
	<li>Select Change Wired Network Settings.</li>
	<li>Select Change Mode and press Enter to change it to Static.</li>
	<li>Select Copy Current Address to Static. Make a note of the IP address listed at the top, you’ll need that in the next step.</li>
	<li>Select Apply to save the changes and restart the network.</li>
	<li>When that’s complete, select Exit to restart the device one more time.</li>
</ol>
After the network settings are configured, your Pi will restart again. Next, install the Pi-Hole software (this can take a while, it took about 20-30 minutes for me), then restart one final time. Once it restarts, the ad blocking software will be run automatically, so all you need to do is set up your computers.
<h3>Step Four: Point Your Devices to the Raspberry Pi for DNS</h3>
<figure class="js_marquee-assetfigure align--bleed">
<div class="img-wrapper lazy-image ">
<div class="img-permalink-sub-wrapper img-permalink-sub-wrapper--nobackground">

&nbsp;
<h4><strong>Android</strong></h4>
<ol>
	<li>Open Settings.</li>
	<li>Select Wi-Fi.</li>
	<li>Long press on your current network and select Modify Network.</li>
	<li>Tap Show Advanced Options.</li>
	<li>Change the IP Settings to Static.</li>
	<li>Enter your Raspberry Pi’s IP address under the DNS field.</li>
</ol>
<h4><strong>iOS</strong></h4>
<ol>
	<li>Open Settings.</li>
	<li>Select Wi-Fi and tap your home network.</li>
	<li>Tap DNS and enter your Raspberry Pi’s IP address.</li>
</ol>
You can also track how the Pi-Hole is doing at blocking ads by heading to: <code>[RaspberryPiIPaddress]/pihole/index.php</code>
<h3>Whitelist Sites</h3>
By default, the Pi-Hole blocks a lot of sites, but you can whitelist your favorite sites, though it’s a little complicated right now. First, you’ll need to head back to your Raspberry Pi. When you boot up the Raspberry Pi and login, you will automatically be at the command line. Here, you can create and edit a text file with the sites you want to <strong>not</strong> block ads on:
<ol>
	<li>From the Raspberry Pi’s command line, type in <code>cd /etc/pihole/</code></li>
	<li>Type in <code>nano whitelist.txt</code> to open a blank text file.</li>
	<li>Type in the URL of any sites you don’t want to block ads on. Press Enter between each entry to put each on a new line. Use both <code>www.site.com</code> and <code>site.com</code> for the sites you don’t want to block.</li>
	<li>Press CTRL+X to save and exit.</li>
	<li>Restart the Raspberry Pi and the changes will take effect.</li>
</ol>
</div>
</div>
</figure>&nbsp;
