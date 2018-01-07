---
layout: post
title: Using OpenLayers To add Animation
date: 2017-07-07 10:31
author: abhinavhanda
comments: true
categories: [Six Months Training]
---
To know what openlayers is <a href="https://openlayers.org/">click here</a> . OpenLayers is better than leaflet if you want to customize your map and make it more interactive.
<h3>Add Animation To maps:</h3>
<code>view.animate()</code> is used to add one or more animations. For a example of adding animation <a href="http://openlayers.org/en/latest/examples/animation.html">click here</a>.

Here if you want to give your cities, just replace london to city you want to add. After replacing london with your city change longitude and latitude in line :
<pre class=" language-markup"><code id="example-source" class=" language-markup"><span class="token script language-javascript"> <span class="token keyword">var</span> london <span class="token operator">=</span> ol<span class="token punctuation">.</span>proj<span class="token punctuation">.</span><span class="token function">fromLonLat</span><span class="token punctuation">(</span><span class="token punctuation">[</span><span class="token operator">-</span><span class="token number">0.12755</span><span class="token punctuation">,</span> <span class="token number">51.507222</span><span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">;</span></span></code></pre>
Here enter your cities longitude and latitude. Also, change the zoom level according to your requirement.
<h3>My Output:</h3>
<img class="alignnone size-full wp-image-379" src="https://abhinavhanda.files.wordpress.com/2017/07/screenshots.png" alt="screenshots" width="1366" height="768" />

Here, I have used zoom level 16 and longitude and latitude of my college and P.A.U. and nearby area.

If you want to take screenshot and use LUbuntu install scrot and use command :
<pre> scrot -e 'mv $f ~/Pictures/screenshots'</pre>
<h2>To add Flight Animation:</h2>
<a href="http://openlayers.org/en/latest/examples/flight-animation.html">Flight Example</a> will provide you example to learn about Flight Animation. Just change the area you want to view,change the areas longitude and latitude and zoom level.
<pre> target: 'map',
 view: new ol.View({
 center: ol.proj.fromLonLat([78.9629, 20.5937]),
 zoom: 12
 })
 });</pre>
<h3>OUTPUT:</h3>
<img class="alignnone size-full wp-image-398" src="https://abhinavhanda.files.wordpress.com/2017/07/flights.png" alt="flights.jpeg" width="1366" height="768" />
