<!--Grading policy at: https://docs.google.com/document/d/1anCzhzfZUNXD713Z1PqBDSAO_tU2PbZUpvT6zi3Y0jQ/preview-->
# Entry 4
##### 4/22/21

I am very proud to say that I'm very close to finishing my Minimal Viable Project(MVP). I was very worried that I wouldn't be able to finsih my project in time, luckliy that isn't the case. I had to derail from what I had originally planned on doing for my project, but doing that pushed me forward more than what I could have imagined. I went back to the <a href = "https://learn.ml5js.org/#/reference/image-classifier">ML5 website</a>,and started looking around for resources I could use to help me complete my project. That's when I found the link to <a href = "https://teachablemachine.withgoogle.com/train">Google's Teachable Machine</a>(GTM). I had been purposely avoiding using this because I believed it would be easier to use a pre trained model and work around that. For GTM you would have to provide the sample images yourselves, which is the biggest problem with making machine learning models. You would need hundreds of samples to give your model, in order for it to somewhat accurately identify the image out in the real world. Even with all those drawbacks it was actually easier to take this route. To my surprise GTM works well with a variety of platforms including <a href = "https://p5js.org/">p5.js</a>. This was like a life saver for me, now I wouldn’t have to figure out how to add to a pre trained model, and clutter up my workspace. GTM gives you start up code, and is very helpful with comments throughout the code. 

```javascript
// Classifier Variable
let classifier;
// Model URL
let imageModelURL = 'https://teachablemachine.withgoogle.com/models/9l6kI7n4j/';

// Video
let video;
let flippedVideo;
// To store the classification
let label = "";

// Load the model first
function preload() {
  classifier = ml5.imageClassifier(imageModelURL + 'model.json');
}

var bView = {//Uses the back camera, can be used for front camera
    audio: false,
    video: {
      facingMode: {
        exact: "environment"
      }
    } 
};
var fView = { //code for front camera, "VIDEO" can also be used
    audio: false,
    video: {
      facingMode: {
        exact: "user"
      }
    } 
};
function setup() {
  createCanvas(320, 260);
  // Create the video
  video = createCapture(bView);
  video.size(320, 240);
  video.hide();

  flippedVideo = ml5.flipImage(video)
  // Start classifying
  classifyVideo();
}
```


[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)