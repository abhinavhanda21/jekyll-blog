---
layout: post
title: Adding Icon's to OSM using Mapnik
date: 2017-06-27 06:40
author: abhinavhanda
comments: true
categories: [Six Months Training]
---
If you are not familiar with Mapnik, then please  read my previous blogs. This blog is to add icon's to your map.
<h3>STEP 1</h3>
Download icon's you want to add to your map. You can use link : http://www.flaticon.com/packs/material-design
<h3>STEP 2</h3>
Add following code, and attach your shapefile or osm file in parameter.
<pre>&lt;Style name="points_layer"&gt; 
 &lt;Rule&gt;
 &lt;MaxScaleDenominator&gt;250000&lt;/MaxScaleDenominator&gt;
 &lt;Filter&gt;'building'&lt;/Filter&gt;
 &lt;PointSymbolizer file= "/home/abhinav/Desktop/ldh/shapefile/shape/buildings.png" type="png" width="16" height="16" /&gt;
 &lt;/Rule&gt; 
 &lt;Rule&gt;
 &lt;MaxScaleDenominator&gt;250000&lt;/MaxScaleDenominator&gt;
 &lt;Filter&gt;'hostipal'&lt;/Filter&gt;
 &lt;PointSymbolizer file= "/home/abhinav/Desktop/ldh/shapefile/shape/hospital-marker.svg" type="png" width="16" height="16" /&gt;
 &lt;/Rule&gt;
 &lt;Rule&gt;
 &lt;MaxScaleDenominator&gt;250000&lt;/MaxScaleDenominator&gt;
 &lt;Filter&gt;'gedi'&lt;/Filter&gt;
 &lt;PointSymbolizer file= "/home/abhinav/Desktop/ldh/shapefile/shape/gedi.png" type="png" width="16" height="16" /&gt;
 &lt;/Rule&gt;
 &lt;Rule&gt;
 &lt;MaxScaleDenominator&gt;250000&lt;/MaxScaleDenominator&gt;
 &lt;Filter&gt;'school'&lt;/Filter&gt;
 &lt;PointSymbolizer file= "/home/abhinav/Desktop/ldh/shapefile/shape/school.png" type="png" width="16" height="16" /&gt;
 &lt;/Rule&gt; 
 &lt;/Style&gt; 
 &lt;Layer name="points_layer" &gt;
 &lt;StyleName&gt;points_layer&lt;/StyleName&gt;
 &lt;Datasource&gt;
 &lt;Parameter name="type"&gt;shape&lt;/Parameter&gt;
 &lt;Parameter name="file"&gt;points.shp&lt;/Parameter&gt;
 &lt;/Datasource&gt;
 &lt;/Layer&gt;</pre>
<h2>OUTPUT:</h2>
Here is a zoomed image of rendered output after adding icon's to map.

<img class="alignnone size-full wp-image-292" src="https://abhinavhanda.files.wordpress.com/2017/06/screenshot-from-2017-06-27-1151361.png" alt="Screenshot from 2017-06-27 11:51:36.png" width="1294" height="664" />
