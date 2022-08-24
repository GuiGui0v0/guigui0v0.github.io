---
layout: post
title:  "Final Project"
date:   2022-08-20 17:16:57 +1000
categories: jekyll update
---
### P5 Sketch
<iframe width=600 height=400 src="https://editor.p5js.org/GuiGui0v0/full/uoZmPl8K_"></iframe>"> </iframe>

### Code Comments

{% highlight ruby %}
function setup() {
//runs once, at the start

createCanvas(576, 324);
//Creating a canvas
//576 pixels wide & 324 pixels tall


colorMode(RGB, 1);
//Using the RGB color model
//Change the numerical range used for specify between 0 and 1
  

noStroke();
//no outline
}

function cosn(v) {
return cos(v * TWO_PI) * 0.5 + 0.5;
//Define a new function block called consn 
// The function block returns 0.5 times the cosine value of V*2PI plus 0.5
}

function invCosn(v) {
return 1 - cosn(v);
//Define a new function block called invCosn 
// The value returned by the function block is 1- cosn(v)
}

const dotSize = 0.1;
const radius = Math.sqrt(0.5) + dotSize;
const PHI = (1 + Math.sqrt(5)) / 2;
//respectively define dotsize, radius and PHI as specific values
//The value of dotsize is set to 0.1
//The value of constradius is set to root number 0.5+0.1 
// PHI value of phi is set to the sum of root numbers 5+1 divided by 2

var t;
const frames = 1000;
//Define variable t 
// Define the value of frames as 1000

var font1, font2;
function preload(){
  font1=loadFont("Boldfinger.ttf");
 font2=loadFont("armedlightninghalf.ttf");
  
}

function draw() {
//Start drawing the pattern
  
t = fract(frameCount / frames);
//The pattern in draw will update the drawn pattern content in real time according to the change of frame rate
//Set the value of t to the value obtained by dividing the number of frames in which the program is running by 1000
  
scale(width, height);
background(0);
fill(1);
//Scale the overall pattern, where the scaling coefficients in the x-direction and y-direction are width and height respectively
//Set the background color of the canvas to black
//The pattern is drawn with a dark gray color of 1

const count = 800 * invCosn(t);
for (let i = 0; i < count; i++) {
//loop 800 * invCosn(t) times
const f = (i / count) * 2;
const a = i * PHI;
const dist = f * radius;
//Set the number of circular patterns to count
//The number of counts is a value that is constantly changing, so that the overall pattern can be constantly changed
//Define f as the value obtained by dividing i by count
//Define the value of a as the product of i and PHI
//Define dist as the product of f and radius
//The three variables are related to each other to form a pattern of change  
  
const x = 0.5 + cos(a * TWO_PI) * dist;
const y = 0.5 + tan(a * TWO_PI) * dist;
//Define the x-coordinate and y-coordinate of each circular pattern
//Form a series of circularly arranged spheres through the definition of trigonometric functions

const sig = pow(cosn(f - t * 5), 2);
const r = sig * f * dotSize;
//Define sig as the value of the exponential function (cosn(f - t * 5), 2)
//Define the radius r of each center pattern, which is related to sig, f and dotsize

const hue = fract(f * 5 + t);
const sat = 0.1;
const light =0.2;
const clr = color(hue, sat, light);
fill(clr);
circle(x, y, r);

//Set the red hue of the color of the sphere to the value of hue, in which the fract function is used to extract the value of the decimal point of f * 7 + t
//Set the green hue value sat value of the sphere color to 0.7
//Set the blue hue value of the sphere color to a sat value of 1
//Define the color as the clr composed of hue, sat and light
//Fill the clr and draw a circle with a circle position of x, y and a radius of r

}

//the text,draw above, are in the background
//the code below draws the text

fill(255,204,0);
//Set the filling color to (255,204,0) yellow
scale(1/width, 1/height);
//Scale the overall pattern, in which the scaling coefficients in X direction and Y direction are1/width & 1/height

textSize(140);
  //change font size to 140
textFont(font1);
  //Set text font to font1
textAlign(CENTER);
  //change origin of text
text('RMIT',width/2,150);
  //write words on screen
  //Set the content of the text to "RMIT"
//the position of the text content is the coordinate point of width/2,150
  // stores half the width
  
fill (227, 229, 224);
//Set the filling color to (255,204,0) yellow

textFont (font2);
//Set text font to font2
textSize (42);
//change font size to 140
text (`Creative Coding`, width / 2, 200);
  //write words on screen
  //Set the content of the text to "Creative Coding"
//the position of the text content is the coordinate point of width/2,200
text (`Specialisation`, width / 2, 250);
    //write words on screen
  //Set the content of the text to "Specialisation"
//the position of the text content is the coordinate point of width/2,250
  // stores half the width

}

{% endhighlight %}

### Reference
Here are some reference videos and pictures for the production project

-[Bannar moondboard pic](https://www.freepik.com/free-vector/abstract-red-halftone-white-banner-design_7197936.htm#query=red%20dot&position=47&from_view=keyword)

-[Bannar moondboard pic](https://www.freepik.com/free-vector/red-wavy-halftone-background_15681043.htm#query=red%20point&position=4&from_view=search)

-[Text Resource](https://fontmeme.com/fonts/futuristic-fonts-collection/)

-[Color Resource](https://www.w3schools.com/colors/colors_groups.asp)
