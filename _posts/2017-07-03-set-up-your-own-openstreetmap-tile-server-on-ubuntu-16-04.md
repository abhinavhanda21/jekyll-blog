---
layout: post
title: Set up Your Own OpenStreetMap Tile Server on Ubuntu 16.04
date: 2017-07-03 06:27
author: abhinavhanda
comments: true
categories: [Six Months Training]
---
I followed <a href="https://www.linuxbabe.com/linux-server/openstreetmap-tile-server-ubuntu-16-04" target="_blank" rel="noopener">linuxbabe </a> link to set my tile server so I will not go into much detail regarding the setup instructions, For that you can follow that link.
<h3><strong>IMPORTANT THINGS:</strong></h3>
<ul>
	<li>You don't need big files. I used my cities area. You can download the area you want to show from this <a href="https://extract.bbbike.org/">link</a> and insert your downloaded file in step step 4 of <a href="https://www.linuxbabe.com/linux-server/openstreetmap-tile-server-ubuntu-16-04" target="_blank" rel="noopener">linuxbabe </a></li>
	<li>Make sure you are using latest version's of mapnik(v3), postgresql(9.6), openstreetmap-carto(v4.0.0)</li>
	<li>If  you use openstreemap-carto version 4.0.0. then you need to run following commands to generate stylesheet:</li>
</ul>
<pre>python get-shapefiles.py

carto project.mml &gt; style.xml</pre>
<h3>Errors :</h3>
<ul>
	<li>If you get error while installing mod_tile, make sure libtool is installed if not then install it.</li>
	<li>If you get error Socket bind failed for: /var/run/renderd/renderd.sock Then run this command:
<pre>sudo chown osm:osm /var/lib/mod_tile</pre>
This command will give permissions to the user you created, in my case it was osm.</li>
	<li>If you get error in make while compiling mod_tile follow:  https://help.openstreetmap.org/questions/13689/problem-with-mod_tile-make</li>
	<li>If you are facing any issue related to rendering of file then you can use this command:</li>
</ul>
<pre>renderd -f -c /usr/local/etc/renderd.conf</pre>
<ul>
	<li>If you want to pre-render the tiles so that your processor doesn’t do processing everytime you zoom-in then you can do it via:</li>
</ul>
<pre>render_list -m default -a -z 0 -Z 10</pre>
<img class="alignnone size-full wp-image-352" src="https://abhinavhanda.files.wordpress.com/2017/07/gndec.png" alt="gndec.png" width="1291" height="584" />
