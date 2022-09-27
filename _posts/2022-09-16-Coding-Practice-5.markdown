---
layout: post
title:  "Coding Practice 05"
date:   2022-09-16 16:28:57 +1000
categories: jekyll update
---
### P5 Sketch
<iframe width=800 height=800 src="https://editor.p5js.org/GuiGui0v0/full/mMMXWUmJ5"></iframe>

### Concept  
This project creates an interactive project by looping, and the user can adjust the speed and shape of the pattern change from clockwise movement to counterclockwise movement according to the interaction with the pattern.

### Code Comments

{% highlight ruby %}

let gap = 25;
let cirNum = 30;
let cirSize = 200;
let angle = 0;
let ptNum =10;
let rectSize =600;

function setup() {
  createCanvas(windowWidth,windowHeight);
  angleMode(DEGREES);
}

//Draw loops forever
function draw(){
  background('black');
// a customized shape for mouse
  noCursor();
  noStroke();
  fill('white')
  circle(mouseX,mouseY,10);

//main cicle graph
  push();
  translate(width/2,height/2);
  rotate(angle);
  angle = angle+map(mouseX,0,width,-0.1,0.1);
  noFill();
  stroke('#3F51B5');
  strokeWeight(10);

//for loop
//Set start and end
//Set how much it increments each time
  for (let i = 0; i<cirNum; i++) {
    arc(0,0,cirSize + gap * i,cirSize + gap * i,angle * i,360-angle/2);
  }
}

{% endhighlight %}

### Reference
Here are some reference videos and pictures for the production project

-[Color Resource](https://www.w3schools.com/colors/colors_groups.asp)
-[Tutorial Video](https://www.youtube.com/watch?v=QjCtbMNLRuc&list=PLA4rGu8NPxE_VigzfGujzrJf9LZv7tx_I&index=6&t=1353s)
