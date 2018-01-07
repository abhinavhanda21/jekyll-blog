---
layout: post
title: Using .htaccess File
date: 2017-07-28 18:32
author: abhinavhanda
comments: true
categories: [Six Months Training]
---
.htaccess is a configuration file for use on web servers running the Apache Web Server software. When a .htaccess file is placed in a directory which is in turn 'loaded via the Apache Web Server', then the .htaccess file is detected and executed by the Apache Web Server software. These .htaccess files can be used to alter the configuration of the Apache Web Server software to enable/disable additional functionality and features that the Apache Web Server software has to offer. These facilities include basic redirect functionality, for instance if a 404 file not found error occurs, or for more advanced functions such as content password protection or image hot link prevention.

To create a simple .htaccess file just go the directory of your choice and copy following lines into it:
<pre>AuthName "Development"
AuthUserFile /home/abhinavhanda23/public_html/animation/FILE/.htpasswd
AuthType basic
Require valid-user</pre>
Here you can see I have given path to a .htpasswd file. This .htpasswd file has the username and password which will be used to view the directory on server.

Use http://www.htaccesstools.com/htpasswd-generator/ to create your disered  user and password. After that just cahnge the location of .htpasswd file. .htpasswd file can be stored anywhere on server.

In the last just give correct permissions to your .htaccess and .htpasswd file

Use command: chmod a+x .htaccess and chmod a+x .htpasswd
<h2>Problems faced:</h2>
&nbsp;

Permission denied:Could not open password file:/home/abhinavhanda23/public_html/animation/FILE/.htpassw
<h2>Solution:<img class="alignnone size-full wp-image-555" src="https://abhinavhanda.files.wordpress.com/2017/07/a.jpeg" alt="a.jpeg" width="1366" height="768" /></h2>
My friend <a href="https://amritpals.com/">Amritpal Singh</a> helped me to solve this problem. He gave following permissions to the files:

-rw-rw-r-- 1 abhinavhanda23 abhinavhanda23 129 Jul 28 18:44 .htaccess
-rw-rw-r-- 1 abhinavhanda23 abhinavhanda23 88 Jul 28 18:48 .htpasswd
