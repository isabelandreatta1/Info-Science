**Monday 6th April 2020**


**What did we do**


In this assignment, we had to do three major tasks. The first task was to practice and further understand for loop, this helps us with repeating a sequence. This task was further divided into the three smaller tasks: a program that prints 100 bears (1-100), a program that counts the years from 1900-2000 and a program that prints the conversion from celsius to farenheit (from 0 - 100 C). The second task we had to complete was to figure out how to add a bargraph that shows the number of people infected and the number of those healthy, the bar graph had to include numbers. We also had to add a counter for how many times the simulation has ran, or the iteration number. The final task was to fill out a table which included five different runs of the simulation and recording number of people moving and number of iterations until all population is infected. 

**What we learnt**

**What questions do I have** 

| Case Number  | Number of people moving |Population size | Number of iterations until all infected | 
| ------------- | ------------- | ------------- | -------------  | 
| 1  | 1 |  25 | 1279 | 
| 2 | 2 | 25 | 
| 3 | 4 | 25 | 
| 4 | 8 | 25 | 
|5 | 16 | 25 | 

**What conclusion can you draw from the simulations you run in step 3. Explain.**


**Propose another table of simulations. Variables we can change include: population size, distance of infection, movement size, number of people moving.** 


1. Code for bear 
```py 
#repeat 100 times
for b in range(101):
    print'bears',(b) #1,2,3,4...100 
    
``` 
2. Code for year 
```py
for b in range(1900,2001):
    print'The year is',(b) #1,2,3,4...100 
```
3. Code for Celsius to Farenheit 
```py 
for c in range(100):
    f = c * 1.8 + 32 #formula, had to change 9/5 from fraction to decimal 
    print c,'C are','F', f
```
4. Code for coronavirus simulation & bar graph/counting roll 
```py 
#defintions of variables
x = []
y= []
h = [False, True] #False => infected 
hi = 0 #healthy individual
uh = 0 #unhealthy individual
c = 0 
bar = 0 

    
def setup():
    size(500,500)
    for i in range(25):
          x.append(random(0, 500))
          y.append(random(0, 500))
          h.append(True) #All Health 
          barGraph()
          
def distance(x1,x2,y1,y2):
    a = (x1 - x2) 
    b = (y1- y2)
    c = sqrt(a**2 + b**2) 
    return c #output of function 
    
def draw():
    background(255)
    strokeWeight(2)
    global x, y, hi, uh, c, bar
    barGraph()
    c += 1
    if hi == 25:
        con -= 1
    
    #First individual 
    for ind in range(len(x)):
        if h[ind] == True:
            fill(255)
        else:
            fill(255,0,0) #infected

        circle(x[ind],y[ind],40)
        #calculate the distance from the neighbour 
        for nei in range(len(x)):
            if nei == ind:
                continue 
            d = distance(x[ind],x[nei],y[ind],y[nei]) 
            if d < 40 and(h[nei] == False  or h[ind] == False): 
                           #infection happens  
                           h[ind] = False
                           h[nei] = False 
        #move individuals
        x[ind] = x[ind] + random(-10,10)
        y[ind] = y[ind] + random(-10,10)
        
        if x[ind] > 500:
            x[ind] = 500
        if x[ind] < 0:
            x[ind] = 0 
        if y[ind] > 500:
            y[ind] = 500
        if y[ind] < 0:
            y[ind] = 0
            
    delay(75) 
        
    uh = 0
    hi = 25
    for bar in range (25):
        if h[bar] == False:
            uh += 1 
            hi -= 1
            
    textSize(10)
    fill(0)
    text('Infected', 445, 478)
    text('Healthy', 445, 458)
    text(c, 80,470)
    text("Iteration #:", 20, 470)
        
def barGraph():
    strokeWeight(1)
    stroke(0)
    fill(255,0,0)
    rect(440,470, - uh*2,8) #bar graph for those infected
    fill(255)
    rect(440,450, - hi*2,8)  #bar graph for those healthy      

```
