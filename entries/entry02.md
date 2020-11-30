# Entry 2
##### 12/1/22

For my project I have decided to use _**Ml5**_ a machine learning tool for the web, that runs in your web browser. 
I have chosen this tool because it perfectly suits my needs. I have done some tinkering with it, and it is challenging enough for me to explore while having somewhat of an understanding of the code. 
I have come across many machine learning videos, separate from Ml5 with useful concepts to help me understand it better.
However I found the videos listed on the <a href="https://ml5js.org/">_**Ml5 website**_</a> to be more useful in <a href="https://www.youtube.com/watch?v=jmznx0Q1fP0">understanding machine learning.</a>

To see what I can do with this tool I followed one of their video tutorials <a href="https://www.youtube.com/watch?v=8HEgeAbYphA&list=PLRqwX-V7Uu6YPSwT06y_AEYTqIwbeam3y&index=15">**Training a Neural Network.**</a>
I didn’t completely understand everything that was going on, further research, and testing will have to be done in order to properly grasp it. Some key concepts however, I do understand.
```javascript
function setup() { //this whole thing runs when starting
  createCanvas(400, 400); //canvas size 

  let options = { //options holds values below subject to change
    inputs: ['x', 'y'], //The # of inputs(things) that will be tested, can also hold #
    outputs: ['label'], //The result that comes after testing 
    task: 'classification', //1 of 3 types of thing a learning program can do
    debug: 'true' //visualization of training model
  };

  model = ml5.neuralNetwork(options); //Model now has the value of things listed above
  background(255); //Background color
}
```

In the code  above is a placeholder for values, this is one the most important parts in training a model to learn. 
This is needed to define what type of task the computer will be learning, along with how many different inputs the computer will be taking at once.
The `let options=` defines a variable that will hold all the values in the **{ }**. This variable is used throughout the code and changes depending on the situation.
The `inputs:` and `outputs:` are the placeholders for the various values you will be giving the computer. `Task` just tells the computer if you are going to be doing classification, regression for image classification.
Finally `debug` is a visual representation of the model learning that appears in a table format and graph.

In the **Engineering Design Process** I’m on _Define the problem_ and _Research the problem_. Last entry I talked about how I wanted to do a therapy chat bot.
I still would like to do that however I don't believe with my current knowledge and skills that I would be able to complete that big of a project in the given time. 
Instead I’m thinking about designing a program that can identify a variety of insects given a photo. I plan for this program to be used inside houses for when people don't know whether an insect is dangerous or not, and how to approach it.
I thought of this idea when I got called down to kill a spider I didn’t regonzie. After further research I found out it was a brown widow, a relative to the black widow, but not as dangerous. 
I think this project will help with the bad stigma around bugs, and not all of them should be killed on sight.

The **Skills** I worked on are, _Consideration_, and _How to Google_. That incident happened a few weeks ago and I didn’t think of that idea until recently.
My _Consideration_ went up from before, because now I’m thinking about the wants of other people, and how the program will affect them.
While a therapy bot would be useful I don’t feel like it would be used as much as a program that can help you identify unidentified insects.
I also further developed _How to Google_. I took time to figure out what that spider was based on the small features on it, like it’s color, size, and dot pattern. 
A computer would be able to do this faster than a human can, and with much more accuracy. 

[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)