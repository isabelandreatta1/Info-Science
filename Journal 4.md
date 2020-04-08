 **Thursday 2nd April 2020**
 
 What are some ways in which Computer Science can help the fight against Covid-19?
In your opinion, should people enable access to the resources of their personal computers as tools for research? Are there any risks?


 There is still a lot that is unknown about the coronavirus, with scientists having limited understanding of how it works and technology in helping them find out. One feasible technique that scientists have been employing is using simulators in order to understand  how proteins work, an essential element to understanding the virus. However, these simulations require a lot of computational power -- much more than what most universities and laboratories have access to. In order to increase the accessibility, instead of doing the calculations through one computer, a Stanford program has alternatively created a network of many computers in order to do calculations. The computers that make up the network pertain to individuals and a software runs once the computer is not being used. The program states that it has heavy security measures from hacking in place. I think it could be a good alternative considering lack of accessibility. There is an urgent need to get information as soon as possible; finding a cure, a vaccine or any methods to prevent/cure of the virus may take months to year(s) and so gathering information is critical. Looking at Fold@Home, the Stanford program, they have done significant work towards understanding protein, however, it is a tedious process, with lack of some holistic “discovery”, and so perhaps this also looks more like a long-term solution rather than a quick one. In terms of risks, I could not find any cases of intrusion even though Fold@Home has been in place for many years, and only could find websites that praise the program’s security for both the research and the volunteers. So the risks are minimal, but it would always be better to use firewalls in order to maximise the security. 


What should be some behaviours (at least 3) that we will need to include in our simulation to be a realistic approximation of the current situation in the world? Explain.


 One change would make our simulation more realistic which replicates human behaviour would be staying in close proximity to those similar to you. This can be done, for example, by assigning individuals nationality, and making them stick more often than those with different nationalities. Or it can be family groups, interests, occupation, age bracket, etc. Another behaviour would be how the virus affects people depending on their age and health. While it is equally contagious, long incubation period and mild symptoms might not deter people from continuing to meet up with people, and so that's another thing to take in account.  Lastly, this relates to the first point, but there are going to be areas of high population density and typically with younger people. These concentrated areas can be thought of as the centre of a city. 
  
  
**What did we do?**


First of all, we had to read and analyse an article which shows how personal computers can help with the coronavirus. More specifically, it presents a program that Stanford created, in which a network of personal computers will complete calculations for models/simulation on understanding protein. Protein is a critical part to understanding the virus and the network is an alternative power as to using one single computer. Secondly, we started on creating a simulation of the coronavirus and how it spreads. We first did this by creating a one circle, which represents one individual, and made it move around with random coordinates. We made it move by, first defining its position, and then coding the coordinates to change by adding a randomised number between -10 and 10. We also added boundary conditions so that the circle can not move outside of the visible plane. The next part of the simulation was to have multiple individuals. Through the tutorials, we learnt how to make this with the “for loop” and by creating a list. Our task was to learn how to create 10 individuals without manually typing the specific coordinates and by using the setup function. With research, coupled with collaborating with other students, we found out that we need to use the append method/function. The append function is a function that inserts items in an already created list. So firstly, we need to create an empty list. We do this by assigning the x and y with nothing so its
```py 
x = [] and y = [].
```
Then, on top of the code for the indinviduals, we use the append function. This is because it will affect everything below it. So: 
```py 
for i in range(10):
    x.append(random(0,500))
    y.append(random(0,500)
``` 
**This means that we have inserted 10 values with any random x and y coordinate between the range of 0 and 500.**


**What did I learn?**


The article was quite helpful, in regards to both learning new facts and also pushing our ideas of what “research” is and how we can help with the coronavirus. During this assignment, on the other hand, we were introduced to a few new concepts. The most important concepts we learnt were creating a list in python and the append function, which is used within lists. In addition, because we were instructed to find the information by ourselves, instead of telling us directly, it helped me understand the append function more. I did have struggles, however, with the format (I found the append function but I didn’t know how to apply it in our code) and so I had to rely on other people.  I also ran into other issues because of carelessness, and I was glad that I had to figure out how to fix it by myself. This is because I helped train my precision and also made sure that I double-check what I write. 


**What questions do I have?** 

I am curious to what extent can lists be used and what other situations can they be used and manipulated. Also, to what extent can we make a realistic simulation in processing (of course limited) and if we could try to input some data of a sample group and create a simulation on how it would spread (in a simplified form). I had some struggles with adding an image to Github's repository. 


```py
#defintions of variables
x = []
y= []
    
def setup():
    size(500,500)
    for i in range(10):
          x.append(random(0, 500))
          y.append(random(0, 500))
    
def draw():
    background(255)
    strokeWeight(2)
    global x, y 
    
    #First individual 
    for i in range(10):
        circle(x[i],y[i],40)
        x[i] = x[i] + random(-10,10)
        y[i] = y[i] + random(-10,10)
        
        if x[i] > 500:
            x[i] = 500
        if x[i] < 0:
            x[i] = 0 
        if y[i] > 500:
            y[i] = 500
        if y[i] < 0:
            y[i] = 0

    delay(100) 
    
``` 
