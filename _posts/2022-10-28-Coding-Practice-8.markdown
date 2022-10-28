---
layout: post
title:  "Coding Practice 08"
date:   2022-10-28 16:28:57 +1000
categories: jekyll update
---
### P5 Sketch
<iframe width=800 height=800 src="https://editor.p5js.org/GuiGui0v0/full/RTjCPIcGS"></iframe>

### Concept  
My inspiration for this project comes from the trajectory of the dog chasing the ball. By displaying the work like a yoyo ball, I hope it can be used in the final project, and also considering that the dog likes yellow to create a tail for the circle in the previous project to form a drag shape ideas.

### Code Comments

{% highlight ruby %}
let angle1 = 0;
let angle2 = 0;
let angleV1 = 0.07;
let angleV2 = 0.03;

function setup() {
  createCanvas(windowWidth, windowHeight);
  background(0);
}

function draw() {
  background(0, 5);
  translate(width / 2, height / 2);
  fill(255, 200, 100,1);
 
  stroke(100, 204, 30,200);
  let ampx = (0.9 * width) / 2;
  let ampy = (0.9 * height) / 2;
  let x = map(cos(angle1), -1, 1, -ampx, ampx);
  let y = map(sin(angle2), -1, 1, -ampy, ampy);
  strokeWeight(5);
  line(0, 0, x, y);
  circle(x, y, 32);
  angle1 += angleV1;
  angle2 += angleV2;
}

{% endhighlight %}

### Reference
Here are some reference videos and pictures for the production project

-[Color Resource](https://www.w3schools.com/colors/colors_groups.asp)
-[Tutorial Video](https://www.youtube.com/watch?v=m463X1cqV6s&t=154s)
