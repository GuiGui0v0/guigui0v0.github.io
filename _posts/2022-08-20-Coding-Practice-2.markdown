---
layout: post
title:  "Coding Practice 02"
date:   2022-08-20 17:16:57 +1000
categories: jekyll update
---
### P5 Sketch
<iframe width=500 height=500 src="https://editor.p5js.org/GuiGui0v0/full/p9fkgsD6W"> </iframe>

### Code Comments

{% highlight ruby %}
var circle = 200;
var rot;
var col; 
var freq = 0.000005; 
var cont = 0;
var r;
function setup() { //runs once, at the start
  
  createCanvas(600, 600);
//creating a canvas
//600 pixels wide & 600 pixels tall
}
function draw() { //loops, after setup has run
  background(242);
//Set the background color of canvas to 242 gray white, where 0 represents black and 255 represents white
  
  translate(300, 300);
//Rotate the overall pattern in the center of canvas
  
  rotate(radians(rot));
//Use radians function to change the value of rot from angle system to arc system
  
  ellipseMode(RADIUS);
//Set the mode of drawing circular pattern to radius mode
  
  for (var i=0; i<300; i ++) {
    circle= 200 + 100*sin(millis()*freq*i);
    col=map(circle,150,250,255,60);
    r=map(circle,100,300,10,10);
    
// for loop, a total of 300 times
//Set the radius value of the circle to be related to the value of i
//Use the map function to make col be related to the radius value of the circle
//The value corresponding to the radius value interval of 250,250 is 255 to 60
    
    fill(col,0,300);
    noStroke();
    ellipse(circle*cos(i), circle*sin(i),r,r);    
    rot=rot+0.00005;
//The color mode of filling is RGB mode, the value of r is col, the value of g is 0, and the value of b is 300
//No outline
//Draw a circular pattern
//The x coordinate of the circle is the product of the cosine of the radius circle and i
//The y coordinate of the circle is the product of the sine of the radius circle and i
//The value of rot is increased by 0.0005 per frame
 }	
}
{% endhighlight %}

### Reference
Here are some reference videos and pictures for the production project
<iframe width=500 height=500 src="https://openprocessing.org/sketch/422446"> </iframe>
