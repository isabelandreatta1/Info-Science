March 2

What did we **do**?


Due to the fact that I am not on campus, Dr Ruben sent us a couple videos to choose from where we can do some basic coding. I followed an online tutorial on how to create generative art, meaning that this art that is produced by an “autonomous system” (meaning it makes decisions independently to the creator). The end product will be 1000 differently colored circles, overlapping each other, with a shadow. For this sketch, the variables that I do not control power of is the location of the each individual circle, the direction of the shadow and the specific color for each circle — those have been randomly assigned. The first thing I did was to first create the circle and the shadow. To do that I create a circle and a grey circle of the same size under it, with a bit of It sticking out as if its a shadow. I do this by giving them the same coordinates and then subtract 25 in the circle’s coordinates as to show that it has a slight shift. Then, I learnt that the fourth number I can write when assigning the color of a circle is the opacity. However, the outline of the circle is still visible,so to make it more realistic as a shadow, I can use the “for loop” and create 30 circles that overlaps and decrease in size (all with a low opacity) to make it appear blurry. The next thing I want to do is so it generates many of these circles with shadows. I do that by, again using the for loop, and creating 1000 circles with a random coordinates. The limits of the coordinates for both x and y are 100-800 so it leaves a bit or border in the 1000x1000 set up. The last thing I do is assign the colors. Instead of giving a spefici color to fill in the circle, I give it a random choice to choose any color between a range which I create. Since we are using RGB, if I leave the range from 0,255 for all of them, it gives any color. Since most of the time, the colors clash a lot since there is a large range, I increases the value of the red by 200 and so all the circles will have a warmer tone. 


What did we learn?

This task taught me more about how python in processing works and expanded my understanding of what is possible. Some practical aspects is that I learnt about how I can change the opacity of shapes, how to make things appear burry. Furthermore, I solidified or strengthened my understanding of previous knowledge such as I now understand better how RGB works and how to simplify my code to make it more efficient. 

What questions do I have?


What are other examples of generative art? How would it be able to make this into a gif/in motion? For example, would it be possible to make the shadows move according to a single light source? How can I increase user interaction? Is there any way to create options as so if the user does something (such as click buttons), there are different outcomes. How can I create a reset button? 


Below is my code: 


```py 
def setup():
    size(1000,1000)
    background(255)
    
    for c in range(1000):
        centre_x = random(100,900)
        centre_y = random(100,800)
        #so it doesnt go out of border because size is 1000x1000
        cs = 50

        noStroke()
        fill(15,15,15,2)
        #Creating 30 circles that overlap and decrease in size with low opacity to make appear blurry
        for i in range(30):
            circle(centre_x, centre_y, cs - i*5)
    
    #Draw Circle Side 1 
        stroke(0)
        #increased red value with 200 
        fill(random(200, 255),random(30,255),random(50,255))
        #-25 so there is a shift from the shadow from the circle 
        circle(centre_x - 25, centre_y - 25, cs)

     #opacity, or 5, is out of 255

``` 
