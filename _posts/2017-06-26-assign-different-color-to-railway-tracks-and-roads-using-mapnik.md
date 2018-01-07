---
layout: post
title: ASSIGN DIFFERENT COLOR TO  RAILWAY TRACKS AND ROADS USING MAPNIK
date: 2017-06-26 05:47
author: abhinavhanda
comments: true
categories: [Six Months Training]
---
<h3>STEP 1</h3>
Download required datasource file, It can be a osm file or a shapefile.
<h3>STEP 2</h3>
Create a xml file if you are using shapefile with following code:
<pre>&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;Map background-color="rgba(255,255,255,1)"&gt;
 &lt;Style name="NoOffset"&gt;
 &lt;Rule&gt;
 &lt;LineSymbolizer stroke="rgb(170,255,0)" stroke-width="1" offset="0" smooth="1"&gt;
 &lt;/LineSymbolizer&gt;
 &lt;/Rule&gt;
 &lt;Rule&gt;
 &lt;TextSymbolizer face-name="DejaVu Sans Book" fill="#008000" halo-radius="10" halo-fill="rgba(255, 255, 255, 0.6)" placement="line" clip="true" vertical-alignment="middle" dy="-10"&gt;&lt;![CDATA[[name]]]&gt;
 &lt;/TextSymbolizer&gt;
 &lt;/Rule&gt;
 &lt;/Style&gt;
 &lt;Layer name="NoOffset"&gt;
 &lt;StyleName&gt;NoOffset&lt;/StyleName&gt;
 &lt;Datasource&gt;
 &lt;Parameter name="type"&gt;shape&lt;/Parameter&gt;
 &lt;Parameter name="file"&gt;roads.shp&lt;/Parameter&gt;
 &lt;/Datasource&gt;
 &lt;/Layer&gt;
 &lt;Style name="Offset"&gt;
 &lt;Rule&gt;
 &lt;LineSymbolizer stroke="rgb(255,0,0)" stroke-width="6" stroke-dasharray ='5' stroke-dashoffset ='5' offset="1" &gt;
 &lt;/LineSymbolizer&gt;
 &lt;/Rule&gt;
 &lt;Rule&gt;
 &lt;TextSymbolizer face-name="DejaVu Sans Book" size="10" placement="point" dy="8" fill="black" placement-type="list"&gt;[name] 
 &lt;Placement size="50" dy="-8" fill="blue"/&gt;
 &lt;/TextSymbolizer&gt;
 &lt;/Rule&gt;
 &lt;/Style&gt;
 &lt;Layer name="Offset"&gt;
 &lt;StyleName&gt;Offset&lt;/StyleName&gt;
 &lt;Datasource&gt;
 &lt;Parameter name="type"&gt;shape&lt;/Parameter&gt;
 &lt;Parameter name="file"&gt;railways.shp&lt;/Parameter&gt;
 &lt;/Datasource&gt;
 &lt;/Layer&gt;
&lt;/Map&gt;</pre>
Also, create a python file with following code:
<pre>from mapnik import *

mapfile = 'new.xml'
map_output = '44.png'

m = Map(4*600,4*600)
load_map(m, mapfile)
bbox=(Envelope( 75.7823000,30.8456000,75.9241000,30.9438000))

m.zoom_to_box(bbox)
print "Scale = " , m.scale()
render_to_file(m, map_output)</pre>
NOTE: in bbox=(Envelop (....)) add your files (minimum longitude, minimum latitude, maximum longitude, maximum latitude).

If you are using a osm file just create same xml file as above and replace shape with osm and shapefile with your osm file, Datasource.
<h3>STEP 3</h3>
Now run command: python render.py
<h2>OUTPUT</h2>
<img class="alignnone size-full wp-image-263" src="https://abhinavhanda.files.wordpress.com/2017/06/44.png" alt="44.png" width="2400" height="2400" />

Zooming the above image we can railway tracks with red color and roads with green color.

<img class="alignnone size-full wp-image-267" src="https://abhinavhanda.files.wordpress.com/2017/06/screenshot-from-2017-06-26-111535.png" alt="Screenshot from 2017-06-26 11:15:35.png" width="1258" height="638" />
