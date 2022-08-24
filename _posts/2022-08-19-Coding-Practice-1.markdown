---
layout: post
title:  "Coding Practice 01"
date:   2022-08-19 17:16:57 +1000
categories: jekyll update
---
### P5 Sketch
<iframe width=500 height=500 src="https://editor.p5js.org/GuiGui0v0/full/9FfcY_8gy"></iframe>

### Code Comments

{% highlight ruby %}
function setup() {
  //runs once, at the start

  const size = min(windowWidth, windowHeight);
  createCanvas(size, size);
  //Creating a canvas
  //Set the min value of the window width and height
  //System variable that stores the inner window height and width, it maps to window.innerHeight and innerWidth

  colorMode(RGB, 1);
  //Using the RGB color model
  //Change the numerical range used for specify between 0 and 1

  noStroke();
  //no outline
}

function cosn(v) {
  return cos(v * TWO_PI) * 0.5 + 0.5;
}
 //Define a new function block called consn
 //The function block returns 0.5 times the cosine of V*2PI plus 0.5.

function invCosn(v) {
  return 1 - cosn(v);
}
  //Define a new function block called invCosn
  // The value returned by the function block is 1- cosn(v)

const dotSize = 0.1;
const radius = Math.sqrt(0.5) + dotSize;
const PHI = (1 + Math.sqrt(5)) / 2;
  //Define dotsize, radius and PHI as specific values respectively.
  //The value of dotsize is set to 0.1
  //The value of constradius is set to root number 0.5+0.1 
  // The value of PHI is set to the sum of root numbers 5+1 divided by 2

let t;
const frames = 1000;
  //Define variable t 
  // Define the value of frames as 1000

function draw() {
  t = fract(frameCount / frames);
//Start drawing the pattern
//The pattern in function draw will update the content in real time according to the change of frame rate
//Set the value of t as the number of frames the program runs divided by 1000

  scale(width, height);
  background(0);
  fill(1);
//Scale the overall pattern, in which the scaling coefficients in X direction and Y direction are width and height, respectively
//Set the background color of the canvas to black
//The color of the pattern drawing fill is dark gray with 1

  const count = 1500 * invCosn(t);
  for (let i = 0; i < count; i++) {
    const f = i / count;
    const a = i * PHI;
    const dist = f * radius;
//Set the number of circular patterns to count
//The number of count is a constantly changing number, so that the whole pattern can constantly change
//Define f as the value obtained by dividing I by count 
//Define a as the product of i and PHI
//Define dist as the product of f and radius
//These three variables are related to each other to change pattern

    const x = 0.5 + cos(a * TWO_PI) * dist;
    const y = 0.5 + sin(a * TWO_PI) * dist;
//Define the X coordinate and Y coordinate of each circular pattern
//Form a series of circularly arranged spheres through the definition of trigonometric functions

    const sig = pow(cosn(f - t * 5), 2);
    const r = sig * f * dotSize;
//Define sig as the value of exponential function (cosn(f-t * 5), 2)
//Define that the radius R of each center pattern is related to sig, f and dotsize.

    const hue = fract(f * 7 + t);
    const sat = 0.7;
    const light = 1;
    const clr = color(hue, sat, light);
    fill(clr);
    circle(x, y, r);
// Define the clr composed of Hue, sat and light
//Fill the clr color and draw a circle with X, Y and R radius
//Set the red hue of the spheres color to value, in which the fractional function is used to extract the decimal point value of f * 7+t
//Set the green hue sat value of the spheres color to 0.7
// Set the blue hue sat value of the spheres color to 1
  }
}

{% endhighlight %}

### Reference
Here are some reference videos and pictures for the production project

-[Color Resource](https://www.w3schools.com/colors/colors_groups.asp)

-[Tutorial Video](https://www.youtube.com/watch?v=RrSOv9FH6uo)



