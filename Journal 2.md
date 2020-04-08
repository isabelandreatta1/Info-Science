Thursday February 20

What did we do?
Chess-board Pattern Illusion:

First of all, we created a chess-like pattern by: placing black rectangles with the size of 50x50, 5 per row, and in alternating pattern. We first did this by making the size of the sketch 500x500 and making the background white. Then, we code 9 black lines, all of them with the different increment of 50 in the y axis. In order to repeat the line multiple times, we must use the "for loop". Once we have created the lines, we code the squares alongside the first row by using "for loop" again, coding 5 squares per row. We also noticed that every other row had the same allignment of squares, and so we can do this by changing the y coordinates of the squares by 100 (because each row is seperate by 50 units, having the squares will have an interval by 100 will mean that it will skip one row). Now that we have the squares for the odd rows, we can just copy and paste the same code that we used but instead of having the squares start from (0,0), we change it so it starts at (100,100). With this, we have created the chess-board pattern background. However, we are not finished yet. We then have to add the part where it makes it into an optical illusion. To do this, we want to make it seem that the rows of squares move to the right every time we click. We break this task by creating an offset, which is the shift that occurs when we click. We first make it that every time we click, there will be one shift, and we define the shift/offset as 50. This means that it will move 50 on the x axis. Then we go back to our code of the rectangles, and we add the offset to the x coordinates for our rectangles. With this, then the task is complete and we have a chessboard that the rectangles will move when we click, therefore, creating the optical illusion that the rows are not straight, when in fact they are.

Optical Illusion:

Our next task was to code our own optical illusion based on one that I found on the internet. The optical illusion I chose was a pattern of gradually smaller white circles inside of each other and a red square that was contained by the outline of the largest circle. I first created a grey background and made the canvas size 50x50. Then, using the "for loop" that we learnt this lesson, I was able to create many circles that gradually got bigger. They had to have the same x and y coordinates, but I made the radius of the circle increase by increments of 20. A problem that I encountered was that the the circles would overlap eachother, and so only one large circle was visible. I later found out this was because I was starting from the smallest circle and increasing, and so then when I ran the code, the large circles would overlap. To overcome this issue, I had to start from the largest circle and subtract/decrease the size of the circles. The next step was to create the red square. To find the coordinates and size, I simply used trial and error until I was satisfied with the size. I ran into another issue, this time regarding the square: the square was white by default and so it would cover up the circles. This was a quick and easy fix as I searched up online how to make objects transparent on processing using python and simply had to write "noFill()". At this point, I had finished my optical illusion, however, Dr Ruben further challenged me by asking if I could make it so "every time you click, the size of the square would increase." We had already learnt about offset earlier in class and so I thought it was an appropriate code to use for this task. I created a first offset of 10 for the x and y coordinates of the square. I first gave the x,y coordinates the variable of x and defined it. Then I wrote that for every click, the x,y coordinates value will decrease of 10; that will make the square's top left corner get closer to the corner of the canvas, making it appear larger. Unfortunately, I did have a difficulty in making the bottom right corner of the square get larger and still was unable to figure that out.

what did we learn?
We worked more on our computational skills of breaking down the big issue into smaller problems. For example, when we started the task of creating the chess-like pattern, we broke down the different tasks needed to complete the whole image. I then applied this thinking for the optical illusion. I also always kept a copy of my previous codes (such as the dice one or the chess one) to see if there was anything that I learnt there which I could apply to my new code. I was able to use the "for loop" and the "offset" which we have learnt earlier as to help me with my new code. Furthermore, I was able to get a better grasp of how we can use variables to make code simpler, easier to follow and type.

What questions do I have?
How do I make the right corner of the square move in ratio to the rest of the square? Is there any way to make my code more efficient/simple? How would I make it possible as so the circles would be moving continiously? How would I be able to make shapes in processing that are not regular shapes or are not already set in the library (e.g. if we were to create the shape of a dog or even a semi-circle)? What are the limits to Processing and how would I be able to make it useful?

Code for the chess-board illusion:

```py 

offset = 50 
def mouseClicked():
    global offset
    offset = offset + 1 

def setup(): 
    size(500,500)
    background(255)

def draw():
    lines()
    rectangles()
    
def lines():
    strokeWeight(1)
    stroke(0)
    y = 50 
    for row in range(9):
        line(0,y,500,y)
        y = y + 50
        
def rectangles():
    stroke(255)
    fill(0)
    #These are the even rows 
    y = 0 
    for row in range(5):
        x = 0 
        for s in range(5):
            rect(x,y,50,50)
            x = x + 100 
        y = y + 100
    #These are the odd rows 
    y = 50  
    global offset 
    for row in range(5):
        x = 0 + offset 
        for s in range(5):
            rect(x,y,50,50)
            x = x + 100 
        y = y + 100
        
```
Code for my optical illusion:
```py 

offset = 10
offset_2 = 20 
#for circles use circle(x,y,radius) 

def mouseClicked():
    global offset 
    global offset_2
    offset_2 = offset_2 + 1 
    offset = offset + 1
    
def setup():
    size (600,600)
    
def draw():
    background(180)
    circles() 
    rectangle()
        
def circles():
    stroke(0)
    strokeWeight(3)
    fill(255)
    r = 500
    for radius in range (25):
        circle(300,300,r)
        r = r - 20
        
def rectangle():
    stroke(255,0,0) 
    strokeWeight(5)
    noFill()
    h = 400 + offset_2
    x = 100 - offset 
    global offset 
    global offset_2 
    rect(x,x,h,h)
```
