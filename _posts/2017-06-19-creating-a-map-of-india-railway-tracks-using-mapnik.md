---
layout: post
title: CREATING A MAP OF INDIA RAILWAY TRACKS USING MAPNIK
date: 2017-06-19 11:07
author: abhinavhanda
comments: true
categories: [Six Months Training]
---
<strong>First, fetch datasource from OSM.  To manually create your datasource follow:</strong>

https://docs.oracle.com/cd/E35413_01/doc.722/e35412/ins_post_installation.htm#autoId10

You can also, fetch data from:

http://download.geofabrik.de/asia.html

download .osm.bz2 file. Then unzip  the file and rename it.

After that open python interpreter. Then create map and style it. For, the code go to: https://abhinavhanda.wordpress.com/2017/06/17/mapnik/

Now, give permission to the requried .shp file from your datasource so that it can be executed.  You can check permission status of your file using command: ll and then use:
<pre>chmod 777 /address of file/file.shp</pre>
Now, you can connect your datasource in your python interpreter.

Create a .py file and copy code from: https://abhinavhanda.wordpress.com/2017/06/17/mapnik/ into your .py file.

Your data has been rendered and you will get a .png image as output.

<img class="alignnone size-full wp-image-161" src="https://abhinavhanda.files.wordpress.com/2017/06/india.png" alt="india.png" width="600" height="300" />
