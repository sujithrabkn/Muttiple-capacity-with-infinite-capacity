# EX-05 Multiple server with infinite capacity - (M/M/c):(oo/FIFO)

## DATE : 20-10-2023

## Aim :-
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 10 seconds, serivice time of two lathe machine follow exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](https://user-images.githubusercontent.com/103921593/203238035-1c8109bc-cbf2-4c77-baea-c5b682a752ef.png)

## Procedure :

![image](https://user-images.githubusercontent.com/103921593/203238265-176740b0-eae2-4772-90be-5449869ac9b0.png)




## Experiment:
![280934359-f4d3f7e7-2d36-45e8-a413-d6d9a27b6f7b](https://github.com/sujithrabkn/Muttiple-capacity-with-infinite-capacity/assets/119477857/3d3f3b28-b9f6-4956-92a5-93bf437d89ed)

![280934403-01641eac-ce80-4444-8b19-273b3497d12e](https://github.com/sujithrabkn/Muttiple-capacity-with-infinite-capacity/assets/119477857/764d4401-02c1-48d2-93a8-e83bc166355b)

## Program
```
# Developed by: SUJITHRA B K N
# Reg no:212222230153


import math
arr_time=float(input("Enter the mean inter arrival time of objects from Feeder
(in secs): "))
ser_time=float(input("Enter the mean  inter service time of Lathe Machine
(in secs) :  "))
Robot_time=float(input("Enter the Additional time taken for the Robot
(in secs) :  "))
c=int(input("Number of service centre :  "))
lam=1/arr_time
mu=1/(ser_time+Robot_time)
print("--------------------------------------------------------------")
print("Multiple Server with Infinite Capacity - (M/M/c):(oo/FIFO)")
print("--------------------------------------------------------------")
print("The mean arrival rate per second : %0.2f "%lam)
print("The mean service rate per second : %0.2f "%mu)
rho=lam/(c*mu)
sum=(lam/mu)**c*(1/(1-rho))/math.factorial(c)
for i in range(0,c):
    sum=sum+(lam/mu)**i/math.factorial(i)
P0=1/sum
if (rho<1):
    Lq=(P0/math.factorial(c))*(1/c)*(lam/mu)**(c+1)/(1-rho)**2
    Ls=Lq+lam/mu
    Ws=Ls/lam
    Wq=Lq/lam
    print("Average number of objects in the system : %0.2f "%Ls)
    print("Average number of objects in the conveyor :  %0.2f "%Lq)
    print("Average waiting time of an object in the system : %0.2f secs"%Ws)
    print("Average waiting time of an object in the conveyor : %0.2f secs"%Wq)
    print("Probability that the system is busy : %0.2f "%(rho))
    print("Probability that the system is empty : %0.2f "%(1-rho))
else:
    print("Warning! Objects Over flow will happen in the conveyor")
print("--------------------------------------------------------------")
```

## Output :
![280934558-9e163905-aad0-4b74-9a18-0b41499a698b](https://github.com/sujithrabkn/Muttiple-capacity-with-infinite-capacity/assets/119477857/842e2c35-cea0-44e5-b3e9-eae007ad5b33)

## Result : 
Thus the average number of materials in the system and conveyor, waiting time of each material in the system and conveyor is found successfully.
