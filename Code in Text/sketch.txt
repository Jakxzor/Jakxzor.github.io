//https://p5js.org
//Assigning the original x values for the circle.
let x1 = 250;
let y1 = 250;

//Assigning colour variables so they can be changed later.
let r = 0;
let b = 0;
let g = 0;
//Assigning a diameter variable for the circle.
let diameter = 50;


function setup()
{
  //Creating the canvas
  createCanvas(594, 841);
  //Setting the background to black when the page loads.
  background(0);
  //Calling the button function on load.
  myFunction();
}

function draw()
{

  //Changing the circles x value by a random between -20 and 20.
  x1 += random(-20, 20);
  //Changing the circles y value by a random between -20 and 20.
  y1 += random(-20,20);
  //containing the x value between two numbers.
  x1 = constrain(x1,0,594);
  //Containing the y value between two numbers.
  y1 = constrain(y1,270, 841);
  //Assigning a random number to the colours so the colour is random.
  r = random(255);
  b = random(255);
  g = random(255);

  //Giving the circle no outsie stroke.
  noStroke();
  //Filling the circle with the number generated with the random colours.
  fill(r,g,b,100);
  //Creating the circle using the x,y and diameter variables.
  ellipse(x1,y1, diameter, diameter);

  //Assigning a variable to X to be between 0 and 15.
  let randomX = random(15);
  //Assigning a variable to Y to be between 0 and 5.
  let randomY = random(5);
  //Creating the original x and y co ordinates.
  let originalX = 0;
  let originalY = 0;
  //Filling the rectangles with random colours.
  fill(random(255),random(255),random(255));
  //Loop to create multiple rectangles.
  for (let i = 0;i < 50;i++){

    //Create the rectangle.
    rect(originalX,originalY,20,20);
    //Change the x and y coordinates by a randomx and y.
    originalX = originalX + randomX;
    originalY = originalY + randomY;
  }

}

//Function for the button on mouse click.
function myFunction() {
  //Making sure the circle starts in the middle.
  x1 = width/2;
  y1 = height/2;
  //Wipes the background and makes it black again.
  background(0);
  //Loop to keep creating tiny rectangles over the screen.
  for (let i = 0;i < 400;i++){

    //Fill the rectangles using the random colour maker.
    fill(r,g,b,100);
    //Create the rectangles.
    rect(random(594),random(841),5,5);

  }
}
