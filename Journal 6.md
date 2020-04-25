**Friday April 24**

**What did we do?**
This week we added a new feature to the simulation to make it more realistic: the recovery. This meant that we had to code an x amount of time after the individual is infected in which it will recover. The second part is to then create a bargraph for the recovered individuals. This assingment was particularly difficult so I had was only able to create a third category, but ran into some problems with the recovery section as well as how to assign the bargraph for the recovered. The first step we had to take was to replace all the boolean expressions (truth and false) into string. This way, we could create a third category (the recovery). The next step was to create a list for days and use the append function. Firstly, the way we measured days would be by the amount of iterations. The way it would work is that the program will detect once an individual has recovered once passed an x amount of days. The list for days would be a range from -1 to x (amount of days). -1 would signify the individual is healthy, x is sick and 0 would be recovered. I made the days till' recovery any random integer from 5 to 30. This way it is more realitstic and has an extra automatated feautred. We also had to add "recovery" to the count and colour of individuals. 

**What we learnt?**
In a more technical way, we learnt about string, how to add a third cateogry (for example, previously we had been working with if a else b, but by adding recovery we c an write "if a, elif c, else). 

**What questions do I have?** 


```py
#defintions of variables
x = []
y= []
h = ["Healthy", "Sick","Recovered"] #string is always quotation mark
days = [30,-1]
hi = 0 #healthy individual
uh = 0 #unhealthy individual
ri = 0 #recovered individual
c = 0 
bar = 0 

    
def setup():
    size(500,500)
    for i in range(25):
          x.append(random(0, 500))
          y.append(random(0, 500))
          h.append("Healthy") #All Health 
          barGraph()
          days.append(-1)

def distance(x1,x2,y1,y2):
    a = (x1 - x2) 
    b = (y1- y2)
    c = sqrt(a**2 + b**2) 
    return c #output of function 
    
def draw():
    background(255)
    strokeWeight(2)
    global x, y, hi, uh, c, bar, ri
    barGraph()
    c += 1
    if hi == 25:
        con -= 1
        
    #Create days for individual
    
    #when infected (30 days of iteration) 
    
    
    #First individual 
    for ind in range(len(x)):
        if h[ind] == "Healthy":
            fill(255)
        elif h[ind] == "Recovered":
            fill(152, 176, 245)
        else:
            fill(255,0,0) #infected

        circle(x[ind],y[ind],40)
        #calculate the distance from the neighbour 
        for nei in range(len(x)):
            if nei == ind:
                continue 
            d = distance(x[ind],x[nei],y[ind],y[nei]) 
            if d < 40 and(h[nei] == "Sick"  or h[ind] == "Sick"): 
                    #infection happens  
                    h[ind] = "Sick"
                    h[nei] = "Sick" 
    
    #when infected (Anything between 5 to 30 days)
    days[ind] = int(random(5,30))
    h[ind] = "Sick"
    
    #Change individuals to recovered
    if h[ind] == "Sick":
        days[ind] -= 1 
        if days[ind] == 0:
        # 1 - become "Recovered" 
            h[ind] == "Healthy"
            
            
        #move individuals
        for ind in range(10):
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
        
    delay(50) 
        
    uh = 0
    hi = 25
    ri = 0
    for bar in range (25):
        if h[bar] == "Sick":
            uh += 1 
            hi -= 1
            #recovered individual
            ri #fix this
            
    textSize(10)
    fill(0)
    text('Infected', 445, 478)
    text('Healthy', 445, 458)
    text(c, 80,470)
    text("Iteration #:", 20, 470)
    text("Recovered",445,438)
        
def barGraph():
    strokeWeight(1)
    stroke(0)
    fill(255,0,0)
    rect(440,470, - uh*2,8)
    fill(255)
    rect(440,450, - hi*2,8) 
    rect(440,430, - ri*2,8)
    fill(255)
    #add bargraph for recovered 
         
        
   ``` 
