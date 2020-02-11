# alankylam.github.io
# Data Science Portfolio by Alan Lam

This portfolio is a compilation of projects I created for corporate data analysis and undergraduate courses. 

1. [Oil & Gas Corporate Drilling Data Project](https://alankylam.github.io/#oil--gas-corporate-drilling-data-project)
2. [Reservoir Simulation Model Project](https://alankylam.github.io/#reservoir-simulation-model-project)
3. [Los Angeles Investment Projections](https://alankylam.github.io/#los-angeles-investment-projections)

## Oil & Gas Corporate Drilling Data Project 
### Problem

This project tackled the data integrity issue that caused major discrepancies between theoretical and actual oil well data. 

There were major differences in the software calculated and field captured bottom-holes (BH), the deepest known point of a well, within the corporate repository of over 19,000 wells. 


<img src="images/WellSchematic.PNG" width= "800" />

> Well Schematic for a Horizontal Well

![](images/BH1.PNG)


> 3D Visualization of Bottom Hole Discrepancy  


### Analysis
First, we must understand how drilling data is recorded and visualized. 

Drilling data is collected through measurement-while-drilling (MWD) tools during the drilling process that utilizes electrical impulses to transmit a combination of data. The survey data collected typically consists of measured depth, inclination, and azimuth--or MDINCAZM for short. 


<img src="images/WellSurvey.gif" width= "400">

> Data Acquisition with MWD tools while drilling  


The MDINCAZM data is then visualized using the mathematical formula called the minimum curvature method displayed below.


<img src="images/MinCurve.PNG" width= "600">

> Minimum Curvature Method   


With this in mind, my analysis first focused on the premise that certain sections of the well were most prone to errors.

**Parameters of an Oil Well**
* Vertical  
* Build 
* Lateral
* Azimuth (Cardinal Directions)  

<img src="images/Vertical1.PNG" width= "400">

> Vertical Section   


![](images/BuildSection.PNG)

> Build Section   


![](images/Lateral.PNG)

> Lateral Section   


![](images/Azm.PNG)

> Azimuth (Well Orientation)   


The conclusion from this analysis found that the vertical length was the major culprit. The vertical section of the data set was left out for operational cost cutbacks by decreasing the use of the MWD tool. But, in return, caused data integrity issues back in the office. 

I conducted further analysis on the missing vertical lengths to understand on what magnitude this impacted the BH discrepancy. 

![](images/Vertical.PNG)

> Missing Vertical Section Analysis  

I saw that a larger missing vertical data set for a well did not **directly** lead to a larger discrepancy, but rather, a larger **potential** for error.
> For example: 2 oil wells, each with 2000 ft missing vertical length. You would first assume they would have similar BH errors, but they didn't. One had an error of 150 ft, the other only had an error of 2 ft! Weird! 

To take my analysis further, I was then able to create a heatmap that highlighted BH errors with different combinations of well parameters to further understand explore the issue. 


![](images/Hess1.PNG)
![](images/Hess2.PNG)
![](images/Hess3.PNG)

> Heatmap further analyzing Missing Vertical Length parameter along with other various parameters

### Solution
Next, I began testing for different solutions to minimize the BH difference. 

I began interpolating the missing well data to fill in the data gaps for various wells. After defining interpolation rules, I was able to minimize the BH discrepancy by ~70% (e.g. 50ft BH error to 15ft error).

![](images/Interp.PNG)


I was then able to create a Python script to streamline this process for the corporate repository. 

```
Python Script:

Unfortunately, the initial code built is proprietary. I will update with framework soon.
```


<img src="images/HessResults.PNG" width= "600">

![](images/CorpRepos.PNG)

## Reservoir Simulation Model Project

Under Construction

![](images/ResModel.PNG)

## Los Angeles Investment Projections

Under Construction
