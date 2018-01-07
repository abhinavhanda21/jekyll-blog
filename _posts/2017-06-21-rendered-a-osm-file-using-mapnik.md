---
layout: post
title: RENDERING A OSM FILE USING MAPNIK
date: 2017-06-21 03:47
author: abhinavhanda
comments: true
categories: [Six Months Training]
---
You have mapnik installed and a running python installation on your computer. The next step is to gather the data from OSM.

You can export data directly from osm.org manually:
<ol>
	<li> Go to osm.org</li>
	<li> Search your location or the area you wish to export.</li>
	<li> Click on export on top left corner of your screen.</li>
	<li> Select area manually.</li>
	<li> Click on export.</li>
</ol>
NOTE: while exporting data manually you have to change longitudes and latitudes in render.py file you will create later.

If you want to download large data easily then, go to downloads.bbbkie.org or https://mapzen.com/data/metro-extracts/.

I have Downloaded Ludhiana map manually from osm.org with ( min longitude, min latitude, max longitude, min latitude) value : (75.0833,30.4866,76.4182,31.3935)

Create the main xml file which contains instructions for mapnik about the contents of the map and how to render them. Create the file mapnik_style.xml with the following content:
<pre>&lt;?xml version="1.0" encoding="utf-8"?&gt;
&lt;Map background-color="#f2efe9" srs="+proj=latlong +datum=WGS84"&gt;
 &lt;FontSet name="book-fonts"&gt;
 &lt;Font face-name="DejaVu Sans Book" /&gt;
 &lt;/FontSet&gt;
 &lt;Style name="highways"&gt;
 &lt;Rule&gt;
 &lt;Filter&gt;[highway] &amp;lt;&amp;gt;''&lt;/Filter&gt;
 &lt;LineSymbolizer stroke="#808080" stroke-width="2" stroke-linejoin="round"
 stroke-linecap="round" /&gt;

&lt;/Rule&gt;
 &lt;Rule&gt;
 &lt;Filter&gt;[highway] &amp;lt;&amp;gt;''&lt;/Filter&gt;
 &lt;TextSymbolizer name="[name]" fontset-name="book-fonts" size="9" fill="#0000" halo-radius="1" placement="line" /&gt;
 &lt;/Rule&gt; 
 &lt;/Style&gt;
 &lt;Layer name="highways" status="on" srs="+proj=latlong +datum=WGS84"&gt;
 &lt;StyleName&gt;highways&lt;/StyleName&gt;
 &lt;Datasource&gt;
 &lt;Parameter name="type"&gt;osm&lt;/Parameter&gt;
 &lt;Parameter name="file"&gt;ldh.osm&lt;/Parameter&gt;
 &lt;/Datasource&gt;
 &lt;/Layer&gt;
&lt;/Map&gt;</pre>
Finally, we have to tell mapnik to render the map using the style file. Create a python script render.py with following content:
<pre>#!/usr/bin/env python2

from mapnik import *

mapfile = 'mapnik_style.xml'
map_output = 'mymap.png'

m = Map(4*1024,4*1024)
load_map(m, mapfile)
bbox=(Envelope( 75.0833,30.4866,76.4182,31.3935 ))

m.zoom_to_box(bbox)
print "Scale = " , m.scale()
render_to_file(m, map_output)</pre>
NOTE: while exporting data manually you have to change longitudes and latitudes in render.py file.

Now run command: python render.py
<h2>Problems faced:</h2>
The rendered image turned out to be blank.
<h2>Solution:</h2>
Latitudes and longitudes has to be changed when you change datasource. In bbox=(Envelope( 75.0833,30.4866,76.4182,31.3935 )) the format (min long, min lat, max long, max lat) should be followed.
<h2>Output:</h2>
&nbsp;

Data exported from osm.org manually. Map area is ludhiana.

<img class="alignnone size-full wp-image-196" src="https://abhinavhanda.files.wordpress.com/2017/06/mymap2.png" alt="mymap2.png" width="1024" height="1024" />

To add details to image edit xml file. Replace LineSymbolizer with following:
<pre>&lt;<span class="pl-ent">TextSymbolizer</span> <span class="pl-e">face-name</span>=<span class="pl-s"><span class="pl-pds">"</span>DejaVu Sans Book<span class="pl-pds">"</span></span> <span class="pl-e">size</span>=<span class="pl-s"><span class="pl-pds">"</span>16<span class="pl-pds">"</span></span> <span class="pl-e">placement</span>=<span class="pl-s"><span class="pl-pds">"</span>point<span class="pl-pds">"</span></span> <span class="pl-e">dy</span>=<span class="pl-s"><span class="pl-pds">"</span>8<span class="pl-pds">"</span></span> <span class="pl-e">fill</span>=<span class="pl-s"><span class="pl-pds">"</span>blue<span class="pl-pds">"</span></span> <span class="pl-e">placement-type</span>=<span class="pl-s"><span class="pl-pds">"</span>list<span class="pl-pds">"</span></span>&gt;[name]
    &lt;<span class="pl-ent">Placement</span> <span class="pl-e">size</span>=<span class="pl-s"><span class="pl-pds">"</span>10<span class="pl-pds">"</span></span> <span class="pl-e">dy</span>=<span class="pl-s"><span class="pl-pds">"</span>-8<span class="pl-pds">"</span></span> <span class="pl-e">fill</span>=<span class="pl-s"><span class="pl-pds">"</span>red<span class="pl-pds">"</span></span>/&gt;<span class="pl-c">&lt;!-- Reduces text size and changes offset --&gt;</span>
    &lt;<span class="pl-ent">Placement</span> <span class="pl-e">fill</span>=<span class="pl-s"><span class="pl-pds">"</span>green<span class="pl-pds">"</span></span>&gt;[abbreviated_name]&lt;/<span class="pl-ent">Placement</span>&gt; <span class="pl-c">&lt;!-- size="10", dy="-8", fill="green", shorter text --&gt;</span>
    &lt;<span class="pl-ent">Placement</span> <span class="pl-e">fill</span>=<span class="pl-s"><span class="pl-pds">"</span>orange<span class="pl-pds">"</span></span> <span class="pl-e">dy</span>=<span class="pl-s"><span class="pl-pds">"</span>8<span class="pl-pds">"</span></span>&gt;[nr]&lt;/<span class="pl-ent">Placement</span>&gt; <span class="pl-c">&lt;!-- size="10", dy="8", fill="orange", shortest text --&gt;</span>
&lt;/<span class="pl-ent">TextSymbolizer</span>&gt;</pre>
This change will give Output:

<img class="alignnone size-full wp-image-205" src="https://abhinavhanda.files.wordpress.com/2017/06/mymap4.png" alt="mymap4" width="4096" height="4096" />

Zooming the above image we can see names of different locations.

<img class="alignnone size-full wp-image-207" src="https://abhinavhanda.files.wordpress.com/2017/06/new.png" alt="new.png" width="1269" height="643" />
