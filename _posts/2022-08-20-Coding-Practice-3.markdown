---
layout: post
title:  "Coding Practice 03"
date:   2022-08-20 17:16:57 +1000
categories: jekyll update
---
### P5 Sketch
<iframe width=500 height=500 src="https://editor.p5js.org/GuiGui0v0/full/2wX_FRQzK"> </iframe>

### Concept

The project's concept shows that "simple things can create complex patterns". 
Random maze generator in one line of Commodore 64 Basic [10 PRINT CHR$](https://www.youtube.com/watch?v=m9joBLOZVEo&t=58s) as presented by Casey Reas at the Eyeo Festival in Minneapolis, Minnesota in June 2011. The program uses the PETSCII character set, specifically 205.5 line character codes, plus random 1s or 0s, alternating between the / and \ characters, and then repeats without causing line breaks. I wanted to combine the design between the pattern and the interval, considering showing the letters of RMIT in the final project


### Code Comments

{% highlight ruby %}
let x=0;
let y=0;
let spacing=20;
  //Define variable x,y & space
  

function setup(){
  createCanvas(500,500);
//Creating a canvas
//500 pixels wide & 500 pixels tall
  background(0);
//Set the background color of canvas to black
}
function draw(){
//Start drawing the pattern
  
  stroke(color(0,0,255));
  strokeWeight(10);
//Create dark saturated blue line
//change stroke weight to 10 
  
  if (random(1) < 0.5){
  //Use a probability function to select random numbers between 0 and 1
  //To randomly create forward and backward slashes  
  
 // a line running from mid-top to bottom-right of canvas
 // a line running from bottom-right to mid-top of canvas 
  
    line(x,y,x+spacing,y+spacing);
//The coordinates of the generated line x1 are at 0, the coordinates of y1 are at 0, the coordinates of x2 are at 20, and the coordinates of y2 are at 20    
  }
 // 
  else {
   line(x,y+spacing,x+spacing,y);
//The coordinates of the generated line x1 are at 0, the coordinates of y1 are at 20, the coordinates of x2 are at 20, and the coordinates of y2 are at 0
  }
  
  
  x=x+spacing;
 //every frame move to next 
  
  if(x>width){
    x=0;
    y=y+spacing;
 //Add variable
 // If when x reaches the end is greater than the width, x is reset to 0 
  }
  
}
{% endhighlight %}

### Reference
Here are some reference videos and pictures for the production project

-[Color Resource](https://www.w3schools.com/colors/colors_groups.asp)

-[Book Resource](https://10print.org/)

-[Tutorial Video](https://www.youtube.com/watch?v=bEyTZ5ZZxZs&t=59s)

-[Tutorial Video](https://www.youtube.com/watch?v=m9joBLOZVEo&t=58s)

