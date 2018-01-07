---
layout: post
title: HOW TO REMOTELY CONTROL YOUR RASPBERRY PI
date: 2017-08-14 18:44
author: abhinavhanda
comments: true
categories: [Uncategorized]
---
To make an ssh tunnel from client (VNC Viewer) to server, we will use
<pre>ssh -t -L 5900:localhost:5933 user@third-machine.net</pre>
Here, the command means: connect with ssh to <code>user@third-machine.net</code>, and forward all connection attempts to the <strong>local</strong> <code>5900</code> to port <code>5933</code> on the machine called <code>localhost</code>, which can be reached from the <code>third-machine.net</code> machine.

To make an ssh tunnel from host (VNC server) to server, we will use
<pre>ssh -t -R 5933:localhost:5900 user@third-machine.net</pre>
Here, the command means: connect with ssh to <code>user@third-machine.net</code>, and forward all connection attempts to the <strong>remote</strong> <code>5933</code> to port <code>5900</code> on the machine called <code>localhost</code>, which can be reached from your local machine. This is called reverse ssh tunnel.

After this successful setup, run VNC server at host listening to localhost on port 5900. Then, run VNC viewer at client looking at localhost on port 5900. Tadaa! now you can control the host’s screen. Now let’s see how to do it actually.
<h2>Procedure</h2>
<h3>Setting up VNC server on Ubuntu</h3>
We will be going to use <a href="http://www.karlrunge.com/x11vnc/">x11vnc</a> for our purpose because it makes all the settings very simple for Unix-like systems.

Step 1: Install x11vnc using <code>sudo apt install x11vnc</code>.

Step 2: Run command: <code>x11vnc -ssh username@third-machine.net:33</code>. And you are done with the reverse ssh command and VNC server starts listening to localhost on port 5900. You can also set a password for your VNC server by using <code>-passwd XXXX</code> with the above command. Add <code>-forever</code> to run it forever even when the ssh connection is lost and <code>-shared</code> to share the screen with more than one person. Look for other options with the man command.
<h3>Starting VNC Viewer</h3>
We will be using SSVNC software as a VNC Viewer on the client’s computer. It comes for many platforms. Ubuntu users can download using command: <code>sudo apt install ssvnc</code>. Others can download it from <a href="http://www.karlrunge.com/x11vnc/ssvnc.html#download">here</a>.

Start ssvnc and then:
– select “Use ssh”.
– enter username@third-machine.net:33 in “VNC Host:Display” entry box and enter the password for VNC server in the “VNC Password” entry box.
– click on connect.
– enter the password for your ssh account if asked.
