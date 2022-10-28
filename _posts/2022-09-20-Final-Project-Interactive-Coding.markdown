---
layout: post
title:  "Final Project 02"
date:   2022-09-20 16:28:57 +1000
categories: jekyll update
---
### P5 Sketch
=======
<iframe width=1000 height=1000 src="https://editor.p5js.org/GuiGui0v0/full/WWJF8vsYK"></iframe>

### Concept  
The concept of the whole work is to combine the rhythm of the music to create different visual visual effects, using the lines and the rhythm of the music to simulate the beat. Through the movement design of particles, the feeling of time and space travel is created, and the interstellar atmosphere of the universe is created. The black background has a sense of cosmic depth, and the stars use white particles to create resizing to create a three-dimensional sense of space.

### Process Thinking
Create a function name preload() and add the mp3 file to read the song, play the song in setup() and get its amplitude, listen to all p5sound by default, or use setInput() to listen to a specific sound source. Use beginShape( ) to start recording the vertices of the shape and endShape( ) to stop recording. After visualization the P5.FFT object can return an array based on the analysis of FFT.waveform( ) and FFT.analyze( ):
Each value computed along the time domain by FFT.waveform() represents the amplitude of the waveform at that time sample. 
Each value computed by FFT.analyze() along the frequency domain represents the magnitude at that slice of the spectrum.

### Code Comments

{% highlight ruby %}
var song
//load the song into the variable
var fft
//variable and store the fft object
var particles = []
//create an empty array to keep track of all the particles
//make global variable
function preload() {
  //the setup and draw function will not run until preload function has run
  song = loadSound('Stayslow.mp3')
  //specify a path to the song
}

function setup() {
    //runs once, at the start
  createCanvas(windowWidth, windowHeight);
    //creating a canvas
    //follow widonw width wide & widow height tall
  angleMode(DEGREES)
    // Change the angle mode from radians to degrees
    fft = new p5.FFT()
    //fft is short for fast fourier transform
    //fft will analyze the sound at the exact point of the time and return an array of values
  loop()
}

function draw() {
  background(0)
  //Set the background color of canvas to black
  stroke(255)
  //Set the stroke color of line to white
  strokeWeight(3)
  //Set stroke weight to 3 
  noFill()
  //remove the fill color
  translate(width / 2, height / 2)
  //make the circle at the center of canvas
    fft.analyze()
    amp = fft.getEnergy(20,200)
  var wave = fft.waveform ()
  //variable and store the wavaform date
  //get the actually waveform date to call the waveform method on the fft object
  for (var t = -1; t <= 1; t += 2){
  //create for loop that runs twice
  //where the for loop variable is negative onece the first time
  //where the for loop variable is postitive onece the second time
  beginShape()
  for (var i = 0; i <= 180; i += 0.5){
    //make the waveform a bit more complex by incrementing the for loop by 0.5
	   var index = floor(map( i, 0, 180, 0, wave.length-1))
       //map the floor variable to the index of the wave
       //the value of this index must be an integer
       
       var r = map(wave [index],-1,1,150,350)
       //use the index to map the radius of the circle to the waveform
       //the minimum radius of the circle is 150
       //the maximum radius of the circle is 350
       var x= r * sin(i) * t
       //multiply the x coordinate with t variable
	   var y= r * cos(i)
       //Draw a circular pattern
       //The x coordinate of the circle is the product of the sine of the radius circle and i
       //The y coordinate of the circle is the product of the cosine of the radius circle and i
  vertex(x,y)
      }
  endShape()
      }
  var p = new Particle()
  //create a new particle every frame
    particles.push(p)
  //push the particle to the empty array
  for (let i = 0 ; i< particles.length; i++){
    particles[i].update()
    particles[i].show() } 
  //call the show method to actually see all the particles on the canvas
}

function mouseClicked() {
    //use mouse click function to allow user to star and pause the song
	if(song.isPlaying()){
    //if the song is already playing
      song.pause();
    //click mouse onece to pause the song
      noLoop()
    //use no loop function when song pauses the canvas freezes
	} else {
	  song.play();
    //ckick mouse once to play the song
      loop()
    //use loop function when song play the canvas run
	}
}
class Particle {
  //create a particle object
  constructor() {
    this.pos = p5.Vector.random2D(). mult(250)
    //the positon of the particles
    //defined as vector when particle is created it will be placed randomly at the perimeter of the waveform
    this.vel = createVector(0,0)
    //create velocity and acceleration to make the particles to move
    //the velocity will just be zero when the particles are first created
    this.acc = this.pos.copy().mult(random(0.0001,0.00001))
    //the acceleration will slowly increase the velocity over time
    //the acceleration vector should have the same direction as the position vector by copying the position vector
    //multiply with a low value to makes the acceleration vector be way smaller than the position vector
    //make the particles move randomness by add random values 
    this.w = random(1,7)
    //make the width of particles random change 1 to 7
  }
  update() {
    this.vel.add(this.acc)
    this.pos.add(this.vel)
  }
  show() {
    //show the particle on the canvas
    noStroke()
    //No outline
    fill(255)
    //fill the white color for particles
    ellipse(this.pos.x,this.pos.y,this.w)
    //x-coordinate of the center of the ellipse is at this.pos
    //y-coordinate of the center of the ellipse is at this.pos
    //the width of ellipse is this.w
  }
}
{% endhighlight %}

### Reference
Here are some reference videos and pictures for the production project
-[Code Resource](https://github.com/jeff2957/Music-Visualization--shader-ball-/blob/master/sketch.js)

-[Tutorial Video](https://www.youtube.com/watch?v=2O3nm0Nvbi4&list=PLA4rGu8NPxE_VigzfGujzrJf9LZv7tx_I&index=8)

-[P5 Sound Resource](https://p5js.org/reference/#/libraries/p5.sound)

-[P5 FFT Resource](https://p5js.org/reference/#/p5.FFT)