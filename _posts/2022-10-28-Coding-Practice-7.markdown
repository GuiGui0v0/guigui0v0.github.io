---
layout: post
title:  "Coding Practice 07"
date:   2022-10-28 16:28:57 +1000
categories: jekyll update
---
### P5 Sketch
<iframe width=800 height=800 src="https://editor.p5js.org/GuiGui0v0/full/RTjCPIcGS"></iframe>

### Concept  
I wanted to create a dragging shape for the tail by giving the circle the idea of puppies chasing their own tails. Making the circle increase stay in place will always keep the number in hope to maintain the puppy's attention can be used in the final project.This project is suitable for interacting with humans, it is difficult to interact with animals because it is difficult for them to touch the trackpad and click the buttons to interact.

### Code Comments

{% highlight ruby %}

let balls = [];

function setup() {
  createCanvas(800, 800);
}

function mouseDragged() {
  let r = 40;
  let b = new Ball(mouseX, mouseY, r);
  balls.push(b);
}

function draw() {
  background(0);
  for (let i = 0; i < balls.length; i++) {
  if (balls[i].contains(mouseX, mouseY)) {
      balls[i].changeColor(255);
    } else { 
    balls[i].changeColor(0);
    }
    balls[i].move();
    balls[i].show();
  }

  if (balls.length > 10) {
      balls.splice(0, 1);
  }
}

class Ball {
  constructor(x, y, r) {
    this.x = x;
    this.y = y;
    this.r = r;
    this.brightness = 0;
  }

  changeColor(bright) {
    this.brightness = bright;
  }

  contains(px, py) {
    let d = dist(px, py, this.x, this.y);
    if (d < this.r) {
      return true;
    } else {
      return false;
    }
  }

  move() {
    this.x = this.x + random(-2, 2);
    this.y = this.y + random(-2, 2);
  }

  show() {
    stroke(255);
    strokeWeight(4);
    fill(this.brightness,100);
    ellipse(this.x, this.y, this.r * 2);
  }
}
{% endhighlight %}

### Reference
Here are some reference videos and pictures for the production project

-[Color Resource](https://www.w3schools.com/colors/colors_groups.asp)
-[Resource](https://p5js.org/reference/#/p5/mouseDragged)
-[Tutorial Video](https://www.youtube.com/watch?v=fBqaA7zRO58)
