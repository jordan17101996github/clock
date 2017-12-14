# <h1> clock


![](https://github.com/jordan17101996github/clock/blob/master/Screen%20Shot%202017-12-11%20at%2012.08.42.png)

![](https://github.com/jordan17101996github/clock/blob/master/Screen%20Shot%202017-12-14%20at%2011.32.06.png)

Done on Processing

I attempted to make face clock with the flashing circles for the eyes, but it was difficult to succeed this.



Methods of the clock design:

PFont font;
PFont zFont;
PFont digiFont;
String theText = ":";

void setup() {
background(100);
size(800, 800);

font = loadFont("MalayalamSangamMN-Bold-44.vlw");
zFont = loadFont("YuMin-Demibold-44.vlw");
digiFont = loadFont ("AppleBraille-Pinpoint6Dot-48.vlw");
}

void drawTime() {
  theText = "";
  theText = theText + day();
  
  textFont(digiFont, 44);
  textAlign(CENTER);
  fill(300, 111, 230);
  text("88:88:88", width / 2, height / 2 + 50);
  fill(0, 360);
  text("XX:XX:XX", width / 2, height / 2 + 50);
  
  String theText = "";
  
  theText = theText + hour();
  theText = theText + ":";
  if (second() < 10) { theText = theText + "0";}
  theText = theText + minute();
  theText = theText + second();
  
  text(theText, width / 2, height / 2 + 50);
  
  fill(110, 100, 190);
  if (millis() % 1000 > 500) {
    text(" : : ", width / 2, height / 2 + 50);
  }
}

void drawDate() {
  textFont(digiFont, 64);
  fill(12, 34, 12);
  text(day() + "_" + month() + "_" + year(),
  width / 2, height / 2 + 45);
}

  void draw() {
    background(0, 50, 0);
    textAlign(CENTER);
  
  ellipseMode(RADIUS);  // Set ellipseMode to RADIUS
fill(25, 122, 67);  // Set fill to white
ellipse(50, 50, 30, 30);  // Draw white ellipse using RADIUS mode

ellipseMode(CENTER);  // Set ellipseMode to CENTER
fill(100, 187, 178);  // Set fill to gray
ellipse(50, 50, 30, 30);  // Draw gray ellipse using CENTER mode
 
 beginShape(RADIUS); // Set beginShape to CENTER
fill(255, 55, 198);  // Set fill to 
 triangle(84, 129, 112, 74, 130, 119);
 
 beginShape(CORNER); 
fill(255, 55, 198);  // Set fill to 
 triangle(94, 119, 112, 74, 140, 129);
 
    ellipseMode(RADIUS);  // Set ellipseMode to RADIUS
fill(25, 122, 67);  // Set fill to white
ellipse(150, 50, 30, 30);  // Draw white ellipse using RADIUS mode

ellipseMode(CENTER);  // Set ellipseMode to CENTER
fill(100, 187, 178);  // Set fill to gray
ellipse(150, 50, 30, 30);  // Draw gray ellipse using CENTER mode
  
    //stroke(0, 50);
    //line(0, height / 2, width, height / 2);
    //line(width / 2, 0, width / 2, height);
    
    if (mousePressed) {
      drawDate();
    } else {
      drawTime();
  }
  }
