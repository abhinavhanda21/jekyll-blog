---
layout: post
title: Adding Search Option using Leaflet
date: 2017-07-15 04:20
author: abhinavhanda
comments: true
categories: [Six Months Training]
---
A plugin that adds the ability to search (geocode) a Leaflet-powered map using <a href="https://mapzen.com/projects/search">Mapzen Search</a> or your own hosted version of the <a href="https://github.com/pelias/api">Pelias Geocoder API</a>.

You can download zip file from https://abhinavhanda23.gdy.club/abc.zip and go to examples and edit two-geocoders.html file. The following line will set your view:
<pre id="line1">var map = L.map('map').setView([30.85879, 75.86304], 16);</pre>
Just by changing longitude and latitude and zoom level you will get your required view. OR You can get Leaflet search control that uses OpenCage Data's geocode from this <a href="https://github.com/abhinavhanda21/leaflet-opencage-search">link</a> , after this you need to change default location of your map which can be done by changing longitudes,latitudes and zoom level.
<h2>OUTPUT:</h2>
vist https://abhinavhanda23.gdy.club/search/examples/two-geocoders.html to view my map.

<img class="alignnone size-full wp-image-447" src="https://abhinavhanda.files.wordpress.com/2017/07/screenshotssear.png" alt="screenshotssear.jpeg" width="1366" height="768" />
