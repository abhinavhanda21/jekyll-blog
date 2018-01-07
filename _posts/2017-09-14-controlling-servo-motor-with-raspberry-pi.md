---
layout: post
title: Controlling Servo Motor with Raspberry pi
date: 2017-09-14 22:35
author: abhinavhanda
comments: true
categories: [Uncategorized]
---
<h2>INTRODUCTION</h2>
<p class="rtejustify">A <a href="http://circuitdigest.com/article/servo-motor-basics">Servo Motor</a> is a combination of DC motor, position control system and gears. Servos have many applications in the modern world and with that, they are available in different shapes and sizes. We will be using <strong>SG90 Servo Motor</strong> in this tutorial, it is one of the popular and cheapest one. SG90 is a 180 degree servo. So with this servo we can position the axis from 0-180 degrees.</p>
<p class="rtejustify">A Servo Motor mainly has three wires, one is for positive voltage, another is for ground and last one is for position setting. The <strong>Red wire</strong> is connected to power, <strong>Brown wire</strong> is connected to ground and <strong>Yellow</strong> wire (or WHITE) is connected to signal.</p>
<p class="rtejustify">The table below shows the Servo Position for that particular Duty Ratio. You can get any angle in between by choosing the value accordingly. So for 45º of servo the Duty Ratio should be ‘5’ or 5%.</p>

<table border="1" cellspacing="0" cellpadding="0">
<tbody>
<tr>
<td>
<p class="rtejustify"><strong>POSITION</strong></p>
</td>
<td>
<p class="rtejustify"><strong>DUTY RATIO</strong></p>
</td>
</tr>
<tr>
<td>
<p class="rtejustify">0º</p>
</td>
<td>
<p class="rtejustify">2.5</p>
</td>
</tr>
<tr>
<td>
<p class="rtejustify">90º</p>
</td>
<td>
<p class="rtejustify">7.5</p>
</td>
</tr>
<tr>
<td>
<p class="rtejustify">180º</p>
</td>
<td>
<p class="rtejustify">12.5</p>
</td>
</tr>
</tbody>
</table>
<h2 class="rtejustify">Circuit Diagram:<img class="alignnone size-full wp-image-609" src="https://abhinavhanda.files.wordpress.com/2017/12/servo-control-using-raspberry-pi-circuit-diagram.png" alt="servo-control-using-raspberry-pi-circuit-diagram.png" width="1302" height="621" /></h2>
<h2><strong>CODE:</strong></h2>
<pre>import RPi.GPIO as IO        # calling for header file for GPIO’s of PI
import time                           # calling for time to provide delays in program
IO.setwarnings(False)          # do not show any warnings
IO.setmode (IO.BCM)            # programming the GPIO by BCM pin numbers. (like PIN29 as‘GPIO5’)
IO.setup(19,IO.OUT)             # initialize GPIO19 as an output
p = IO.PWM(19,50)              # GPIO19 as PWM output, with 50Hz frequency
p.start(7.5)                             # generate PWM signal with 7.5% duty cycle
while 1:                                                       # execute loop forever                                    
        p.ChangeDutyCycle(7.5)                   # change duty cycle for getting the servo position to 90º
        time.sleep(1)                                      # sleep for 1 second
        p.ChangeDutyCycle(12.5)                  # change duty cycle for getting the servo position to 180º
        time.sleep(1)                                     # sleep for 1 second
        p.ChangeDutyCycle(2.5)                  # change duty cycle for getting the servo position to 0º
        time.sleep(1)                                     # sleep for 1 second</pre>
Video of the servo motor in action <a href="https://youtu.be/M9UaWI8jRYQ">click here</a>
