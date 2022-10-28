---
layout: post
title:  "Coding Practice 06"
date:   2022-09-16 16:28:57 +1000
categories: jekyll update
---
### P5 Sketch
<iframe width=800 height=800 src="https://editor.p5js.org/GuiGui0v0/full/exkNJwhmk"></iframe>

### Concept  
I use the analyze() function to get the spectrum. It returns an array of magnitude values (between 0 and 255) for the entire spectrum. The spectrum array of the sound file is analyzed by the p5.FFT object. Created a visual "Graphic Equalizer" overall in a minimalist style showing gradients created using black to white.

### Code Comments

{% highlight ruby %}

var song;
var fft;
var button;
var volhistory = [];
var w;

function toggleSong(){
  if (song.isPlaying()){
  song.pause();
  } 
  else{
  song.play();
  }
}

function preload(){
  song = loadSound('stay.mp3');
}

function setup(){
  createCanvas(800,800);
  colorMode(HSB);
  angleMode(DEGREES);
  button = createButton('Play');
  button.mousePressed(toggleSong);
  song.play();
  fft = new p5.FFT(0.9,128);
  w= width / 128 + 2;
}


function draw(){
  background(0);
  var spectrum = fft.analyze();
  console.log(spectrum);
  for (var i=0; i< spectrum.length;i++)
  {
    stroke(255);
    var amp = spectrum [i];
    var y = map(amp,0,256,height,0);
    
    fill(i,255); 
    rect(i * w, y, w, height - y);
  }
}

{% endhighlight %}

### Reference
Here are some reference videos and pictures for the production project

-[Color Resource](https://www.w3schools.com/colors/colors_groups.asp)

-[Tutorial Video](https://www.youtube.com/watch?v=2O3nm0Nvbi4&list=PLA4rGu8NPxE_VigzfGujzrJf9LZv7tx_I&index=2)

-[Music Resource](https://trendybeatz.com/download-mp3/12215/the-kid-laroi-stay-ft-justin-bieber)
