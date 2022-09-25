---
layout: post
title:  "Coding Practice 04"
date:   2022-09-16 16:28:57 +1000
categories: jekyll update
---
### P5 Sketch
<iframe width=500 height=500 src="https://editor.p5js.org/GuiGui0v0/full/MLtknlFC3"></iframe>

### Concept  

### Code Comments

{% highlight ruby %}

var x1=0;
var y1;
var x2;
var y2;
var a=0;
var b=0;
var co=0;

function setup(){
  createCanvas(800,800);
  background(255);
  colorMode(HSB,100);
  frameRate(1000);
}

function draw(){
  x1=map(sin(a),-1,1,20,width-20);
  y1=map(cos(a),-1,1,20,height-20);
  
  x2=map(sin(b),-1,1,20,width-20);
  y2=map(cos(b),-1,1,20,height-20);
  
  stroke(co,100,60,10);
  line(x1,y1,x2,y2);
  
  a=a+.01;
  b=b+.03+cos(b)/120;
  co=co+.005;
}

  {% endhighlight %}