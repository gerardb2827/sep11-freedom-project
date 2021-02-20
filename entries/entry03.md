# Entry 3
##### 2/10/21

I've been working with ML5, and I've run into countless problems as I progressed. I recently moved from <a href="https://repl.it">_**repl.it**_</a> to <a href="https://github.com">_**Github.**_</a> I did this change because github's platform is more versatile, and free.
Soon after the switch I began to realize that ml5 does not work very well with github and my Ide. I’ve run into countless errors when trying to run the startup code in my Ide.
```javascript
 // Initialize the Image Classifier method with MobileNet
const classifier = ml5.imageClassifier('MobileNet', modelLoaded);
// When the model is loaded
function modelLoaded() {
  console.log('Model Loaded!');
}
// Make a prediction with a selected image
classifier.classify(document.getElementById(js/projects/me.jpg)), (err, results) => {
  console.log(results);
};
function setup() {
    createCanvas(400, 400);
}
function draw() {
    background(200);
 }
```
This code ran an error saying `TypeError: Cannot read property 'elt' of null`. I went through many websites to try, and see why I was getting this error. 
From what I understood it had something to do with ML5 not including a part in the cdn link provided in the Get Started section. Unfortunately, I don't remember the website I got the missing link from.
However, when I included that into my index file the error was still there. So I decide to stop working in my Ide and github, and moved to <a href= "https://editor.p5js.org/">_**p5.js Web Editor**_.</a> Ml5 was built to run very well with p5.js, which  is where the 5 in ml5 comes from.
P5.js is very different from what I'm used to working with, so I’m going to have to learn this tool while learning how to navigate p5.js. Luckily ml5 has a useful<a href = "https://editor.p5js.org/ml5/sketches/ImageClassification"> _**link**_</a> for starter code when running in p5.js. 
I ran into a few problems with uploading images, but later learned that it has something to do with a crome extention I have on my comebook. Moving to another computer solved this problem and I was ready to work. This is the code that I have so far:
```javascript 
let classifier;
// A variable to hold the image we want to classify
let img;
function preload() {
  classifier = ml5.imageClassifier('MobileNet');
  img = loadImage('images/mantis.jfif');
}
function setup() {
  createCanvas(400, 400);
  classifier.classify(img, gotResult);
  image(img, 0, 0);
}
// A function to run when we get any errors and the results
function gotResult(error, results) {
  // Display error in the console
  if (error) {
    console.error(error);
  }
  // The results are in an array ordered by confidence.
  console.log(results);
  createDiv('Label: ' + results[0].label);
  createDiv('Confidence: ' + nf(results[0].confidence, 0, 2));
}
```
This code is bringing a pretrained image classifier model called _**Mobilenet**_ in the `preload function`, and giving an image to the model to define. The `setup function` is a set area for the image being classified, and puts it on the screen.
Finally the `gotResult function` is what Mobilenet thinks the image is. _**Mobilenet**_ order's the top 3 things it thinks the image is in confidence scores. This gets logged into the console as an array with a number assinged to it.
The function then takes the first guess which has the highest score and labels the image as that guess. It would look something like this:
 <img src="../images/example-1.JPG">
[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)