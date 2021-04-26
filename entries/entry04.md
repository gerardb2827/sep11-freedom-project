<!--Grading policy at: https://docs.google.com/document/d/1anCzhzfZUNXD713Z1PqBDSAO_tU2PbZUpvT6zi3Y0jQ/preview-->
# Entry 4
##### 4/22/21

I am very proud to say that I'm very close to finishing my Minimal Viable Project(MVP). I was very worried that I wouldn't be able to finsih my project in time, luckliy that isn't the case. I had to derail from what I had originally planned on doing for my project, but doing that pushed me forward more than what I could have imagined. I went back to the <a href = "https://learn.ml5js.org/#/reference/image-classifier">ML5 website</a>,and started looking around for resources I could use to help me complete my project. That's when I found the link to <a href = "https://teachablemachine.withgoogle.com/train">Google's Teachable Machine</a>(GTM). I had been purposely avoiding using this because I believed it would be easier to use a pre trained model and work around that. For GTM you would have to provide the sample images yourselves, which is the biggest problem with making machine learning models. You would need hundreds of samples to give your model, in order for it to somewhat accurately identify the image out in the real world. Even with all those drawbacks it was actually easier to take this route. To my surprise GTM works well with a variety of platforms including <a href = "https://p5js.org/">p5.js</a>. This was like a life saver for me, now I wouldn’t have to figure out how to add to a pre trained model, and clutter up my workspace. GTM gives you start up code, and is very helpful with comments throughout the code. 

```javascript
// Classifier Variable
let classifier;
// Model URL
let imageModelURL = 'https://teachablemachine.withgoogle.com/models/w-i3lGn0r/';

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
This is the main portion of <a href="https://editor.p5js.org/gerardb2827/present/Jh79r6VQd">my project</a> that does all the important work. The first few lines list variables that will be used later on, but the `imageModelURL` is the <a href="https://teachablemachine.withgoogle.com/models/w-i3lGn0r/">source</a> to my model. By clicking on the “metadata.json” at the bottom of the page, you will be brought to the api of the model where it will list all the labels that the model knows. Further down you will see `fView` and `bView` This is where I used the <a href="https://p5js.org/reference/">reference page</a> of p5.js. When the starter code first loaded it would use the front facing camera of the device. This would put you in an awkward position if you wanted to look at a bug that is in front of you. I needed to figure out how to flip the camera around in p5 so it would be more comfortable to the user. After some searching through the reference page I found an example that showed how to use the front, and back camera. You can see this after the `function preload()`, where you see the 2 variables holding both cameras. The `function setup()` is what runs when the page is loaded. This is where you input the frame of the camera, its position, and where your model will be getting information for it to classify. 

In the **Engineering Design Process** I’m on _Test and Evaluate the Prototype_. Now that I have something that works, I need to gather data for the model. This was much harder than I had anticipated. My biggest problem with gathering the data was getting myself clear images. Finding bugs was somewhat difficult to do, but not as hard as taking the picture. I wanted clear images so that when I trained the model the blurriness wouldn't affect the calculations. In order to do that I had to get extremely close to them, and zoom the camera to max. Most times the bugs would just burrow under the soil, and I wouldn't have enough time to get a good image of them. I also had to make sure that I included a variety of different positions, and distances, to avoid <a href = "https://eandt.theiet.org/content/articles/2021/04/ai-bias-is-down-to-people-not-technology/">**AI bias**</a>.<!-- However, I was able to get a decent amount of pictures in the short amount of time I was gathering data, shown below. 

![Images of samples](FDP/sep11-freedom-project/images/Sample-SS.png)-->

The **Skills** I worked on during this time are, _How to Google_ and haveing a _Growth mindset_. Google was my best friend during my work, it helped me solve so many problems. When I first started taking pictures, and tried to upload them, they wouldn’t appear in the GTM. I was very confused why it was like that, so I tried reorganizing the picture linking GTM to my drive, and even switching computers and downloading the files from there. However nothing seemed to work, so I thought to myself, “What’s a <a href = "https://backlightblog.com/iphone-heic-to-jpg">_HEIC file_</a>, and why are my pictures that file type?”. After doing some searching,I discovered that, that is the file type apple chose to use as default, and a lot of things don't support that file type yet. _HEIC_ is basically a way to compress image file size without losing its quality. On that same webpage I found that I would need to download a converter to change it to _JPG_. So that’s what I did and was able to successfully upload the images to GTM. There was a way to make it so that future pictures turn into _JPG_, but I feel like converting it after would keep the quality that I want. My _Growth Mindset_ helped me in moving forward with my project. I could have stayed stubborn, and continued to try with adding onto an existing model. I adapted to my situation, and realized that this wasn’t going to work out, and changed my plan.

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)

