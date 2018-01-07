---
layout: post
title: Enhancement UI of OSM Map
date: 2017-07-18 11:45
author: abhinavhanda
comments: true
categories: [Six Months Training]
---
To add a dropdown button follow this <a href="https://www.w3schools.com/howto/tryit.asp?filename=tryhow_css_dropdown_navbar_click">Link</a>

Add following code to style:
<pre>&lt;style&gt;
.container {
 overflow: hidden;
 background-color: #333;
 font-family: Arial;
}

.container a {
 float: left;
 font-size: 16px;
 color: white;
 text-align: center;
 padding: 14px 16px;
 text-decoration: none;
}

.dropdown {
 float: left;
 overflow: hidden;
}

.dropdown .dropbtn {
 cursor: pointer;
 font-size: 16px; 
 border: none;
 outline: none;
 color: white;
 padding: 14px 16px;
 background-color: inherit;
}

.container a:hover, .dropdown:hover .dropbtn {
 background-color: red;
}

.dropdown-content {
 display: none;
 position: absolute;
 background-color: #f9f9f9;
 min-width: 160px;
 box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
 z-index: 1;
}

.dropdown-content a {
 float: none;
 color: black;
 padding: 12px 16px;
 text-decoration: none;
 display: block;
 text-align: left;
}

.dropdown-content a:hover {
 background-color: #ddd;
}

.show {
 display: block;
}
&lt;/style&gt;</pre>
Then add following code to make sure your animation works:
<pre><span id="line103"></span>&lt;<span class="start-tag">li</span> <span class="attribute-name">id</span>="<a class="attribute-value">Animations</a>"&gt;
<span id="line104"></span>	&lt;<span class="start-tag">a</span> <span class="attribute-name">href</span>="<a class="attribute-value" href="http://abhinavhanda.me/#">#</a>"&gt;Animations&lt;/<span class="end-tag">a</span>&gt;
<span id="line105"></span>	&lt;<span class="start-tag">ul</span> <span class="attribute-name">class</span>="<a class="attribute-value">subnav</a>"&gt;
<span id="line106"></span>		&lt;<span class="start-tag">li</span>&gt;<span class="error" title="Saw “&lt;” when expecting an attribute name. Probable cause: Missing “&gt;” immediately before.">&lt;<span class="start-tag">a</span> <span class="attribute-name">&lt;button</span> <span class="attribute-name">id</span>="<a class="attribute-value">rotate-left</a>" <span class="attribute-name">title</span>="<a class="attribute-value">Rotate clockwise</a>"&gt;</span>clockwise<span class="error" title="Stray end tag “button”.">&lt;/<span class="end-tag">button</span>&gt;</span>&lt;/<span class="end-tag">a</span>&gt;&lt;/<span class="end-tag">li</span>&gt;
<span id="line107"></span>		&lt;<span class="start-tag">li</span>&gt;<span class="error" title="Saw “&lt;” when expecting an attribute name. Probable cause: Missing “&gt;” immediately before.">&lt;<span class="start-tag">a</span> <span class="attribute-name">&lt;button</span> <span class="attribute-name">id</span>="<a class="attribute-value">rotate-right</a>" <span class="attribute-name">title</span>="<a class="attribute-value">Rotate counterclockwise</a>"&gt;</span>anticlockwise<span class="error" title="Stray end tag “button”.">&lt;/<span class="end-tag">button</span>&gt;</span>&lt;/<span class="end-tag">a</span>&gt;&lt;/<span class="end-tag">li</span>&gt;
<span id="line108"></span>		&lt;<span class="start-tag">li</span>&gt; <span class="error" title="Saw “&lt;” when expecting an attribute name. Probable cause: Missing “&gt;” immediately before.">&lt;<span class="start-tag">a</span> <span class="attribute-name">&lt;button</span> <span class="attribute-name">id</span>="<a class="attribute-value">pan-to-main_gate</a>"&gt;</span>Main Gate<span class="error" title="Stray end tag “button”.">&lt;/<span class="end-tag">button</span>&gt;</span>&lt;/<span class="end-tag">a</span>&gt; &lt;/<span class="end-tag">li</span>&gt;
<span id="line109"></span>		&lt;<span class="start-tag">li</span>&gt;<span class="error" title="Saw “&lt;” when expecting an attribute name. Probable cause: Missing “&gt;” immediately before.">&lt;<span class="start-tag">a</span> <span class="attribute-name">&lt;button</span> <span class="attribute-name">id</span>="<a class="attribute-value">pan-to-boyshostel</a>"&gt;</span>Boys Hostel<span class="error" title="Stray end tag “button”.">&lt;/<span class="end-tag">button</span>&gt;</span>&lt;/<span class="end-tag">a</span>&gt;&lt;/<span class="end-tag">li</span>&gt;
<span id="line110"></span>		&lt;<span class="start-tag">li</span>&gt;<span class="error" title="Saw “&lt;” when expecting an attribute name. Probable cause: Missing “&gt;” immediately before.">&lt;<span class="start-tag">a</span> <span class="attribute-name">&lt;button</span> <span class="attribute-name">id</span>="<a class="attribute-value">elastic-to-auditorium</a>"&gt;</span>Auditorium<span class="error" title="Stray end tag “button”.">&lt;/<span class="end-tag">button</span>&gt;</span>&lt;/<span class="end-tag">a</span>&gt;&lt;/<span class="end-tag">li</span>&gt;
<span id="line111"></span>		&lt;<span class="start-tag">li</span>&gt;<span class="error" title="Saw “&lt;” when expecting an attribute name. Probable cause: Missing “&gt;” immediately before.">&lt;<span class="start-tag">a</span> <span class="attribute-name">&lt;button</span> <span class="attribute-name">id</span>="<a class="attribute-value">bounce-to-workshop</a>"&gt;</span>Workshop<span class="error" title="Stray end tag “button”.">&lt;/<span class="end-tag">button</span>&gt;</span>&lt;/<span class="end-tag">a</span>&gt;&lt;/<span class="end-tag">li</span>&gt;
<span id="line112"></span>		&lt;<span class="start-tag">li</span>&gt;<span class="error" title="Saw “&lt;” when expecting an attribute name. Probable cause: Missing “&gt;” immediately before.">&lt;<span class="start-tag">a</span> <span class="attribute-name">&lt;button</span> <span class="attribute-name">id</span>="<a class="attribute-value">spin-to-mba_block</a>"&gt;</span>MBA Block<span class="error" title="Stray end tag “button”.">&lt;/<span class="end-tag">button</span>&gt;</span>&lt;/<span class="end-tag">a</span>&gt;&lt;/<span class="end-tag">li</span>&gt;
<span id="line113"></span>		&lt;<span class="start-tag">li</span>&gt;<span class="error" title="Saw “&lt;” when expecting an attribute name. Probable cause: Missing “&gt;” immediately before.">&lt;<span class="start-tag">a</span> <span class="attribute-name">&lt;button</span> <span class="attribute-name">id</span>="<a class="attribute-value">fly-to-pg_block</a>"&gt;</span>PG Block<span class="error" title="Stray end tag “button”.">&lt;/<span class="end-tag">button</span>&gt;</span>&lt;/<span class="end-tag">a</span>&gt;&lt;/<span class="end-tag">li</span>&gt;
<span id="line114"></span>		&lt;<span class="start-tag">li</span>&gt;<span class="error" title="Saw “&lt;” when expecting an attribute name. Probable cause: Missing “&gt;” immediately before.">&lt;<span class="start-tag">a</span> <span class="attribute-name">&lt;button</span> <span class="attribute-name">id</span>="<a class="attribute-value">pan-to-library</a>"&gt;</span>Library<span class="error" title="Stray end tag “button”.">&lt;/<span class="end-tag">button</span>&gt;</span>&lt;/<span class="end-tag">a</span>&gt;&lt;/<span class="end-tag">li</span>&gt;
<span id="line115"></span>		&lt;<span class="start-tag">li</span>&gt;<span class="error" title="Saw “&lt;” when expecting an attribute name. Probable cause: Missing “&gt;” immediately before.">&lt;<span class="start-tag">a</span> <span class="attribute-name">&lt;button</span> <span class="attribute-name">id</span>="<a class="attribute-value">pan-to-sports</a>"&gt;</span>Sports<span class="error" title="Stray end tag “button”.">&lt;/<span class="end-tag">button</span>&gt;</span>&lt;/<span class="end-tag">a</span>&gt;&lt;/<span class="end-tag">li</span>&gt;
<span id="line116"></span>		&lt;/<span class="end-tag">ul</span>&gt;
<span id="line117"></span>	&lt;/<span class="end-tag">li</span>&gt;
<span id="line118"></span>&lt;/<span class="end-tag">ul</span>&gt;</pre>
<h2>Problems Faced:</h2>
Dropdown button was overlapped by Map's layer and dropdown button was not working.
<h2>Solution:</h2>
My friend <a href="https://amritpals.com" target="_blank" rel="noopener">Amritpal Singh</a> suggested to add following code in style and It worked.
<pre id="line1">&lt;style&gt;
.ol-viewport{
<span id="line26"></span>	z-index:-1;
<span id="line27"></span>}</pre>
<h2>Output:</h2>
<img class="alignnone size-full wp-image-493" src="https://abhinavhanda.files.wordpress.com/2017/07/animation.png" alt="animation" width="1366" height="768" />
