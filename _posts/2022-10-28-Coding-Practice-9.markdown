---
layout: post
title:  "Coding Practice 09"
date:   2022-10-28 16:28:57 +1000
categories: jekyll update
---
### P5 Sketch
<iframe width=800 height=800 src="https://editor.p5js.org/GuiGui0v0/full/-hgfmVVMz"></iframe>

### Concept  
This project transforms the circle into a fast-changing flat figure through the change of frame number, which can produce a series of visual interactions with the viewer. The reference shape is a fill() slow-moving circle, which is visually striking by changing the movement speed and fill and color changes, but not much interactive content

### Code Comments

{% highlight ruby %}

let angle = 0;
let angleV = 0;

function setup() {
  createCanvas(800, 800);
}

function draw() {
  background(0);
  translate(400, 400);
  noFill();
  stroke(100, 100, 240);
  strokeWeight(5);
  let r = map(sin(angle), -1, 1, 0, 200);
  circle(0, 0, r * 2);

  angle += angleV;
  angleV += 0.01;
}

{% endhighlight %}

### Reference
Here are some reference videos and pictures for the production project

-[Color Resource](https://www.w3schools.com/colors/colors_groups.asp)
-[Tutorial Video](https://www.youtube.com/watch?v=m463X1cqV6s&t=561s)
-[Tutorial Video](https://www.youtube.com/watch?v=nicMAoW6u1g&t=586s)

