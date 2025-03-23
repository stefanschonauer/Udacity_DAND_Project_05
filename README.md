# Bike Sharing Data Set Exploration
## by Stefan Schonauer


## Dataset

This data set includes around 180,000 bike rides in the San Francisco Bay Area in February 2019. 
Additional features are departure and arrival stations, geographic coordinates, ride duration, bike data and personal data of the rider. 
Some data types were changed and 197 rows were removed because of mission station information. There were unusual values in the birth year variable.


## Summary of Findings

Rides depend on region and user type. Distribution of departure rides differs dramatically over the 329 stations. 
Additionally, the stations are grouped into three main regions (west, central and east). 
The riding behaviour regarding regions and user types differs a lot. 
The most rides take place in the west region. Central and east region are less relevant regarding number of rides. 
The two user types (customer and subscriber) differ in number an behaviour. 

Furthermore ride behaviour depend on starting hour on the day. 
The main part of rides take place in the west region on working day in the morning and the afternoon by subscribers. 
Rides in the central and east region are a minor part. Rides of customers across all regions differ not regarding day of week. 

Another important aspect is the duration of the rides. The major part of rides take place within the first hour of rent. 
There is a difference in usage behaviour regarding user type and duration. Generally speaking mass of subscribers use the bike 
system for short rides within the first 20 minutes. Customers use the bike system in average for longer trips for around one hour and more.
Duration includes unusual values of high ride duration. I did not treat them as outliers, because they appear as plausible and correct.

My investigation shows that the bike system has its main purpose for commuting on working day in the west region. 


## Key Insights for Presentation

I would like to present my conclusion and the main purpose for commuting. Therefore I focus on regions, user types and day and time of departure. 

I start with the number and distribution of departure stations for my first visualization.

In my second visualization I proceed with the geographical distribution of the stations and the number of departure rides. 
For better readability I changed the legend title to 'Departures'. Furthermore, I changed the scatters with alpha of 0.75 and added size. 
The bigger and darker scatters are the more departures take place.

I finish my presentation with my third and fourth presentation of number of rides relating region, user type, day of week and start hour. 
I changed number of bins and used distances betweens singe bars for better readability.


## Sources

### Wrangling

https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.reset_index.html

https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.dropna.html


### Conditional formating

https://www.dataquest.io/blog/tutorial-add-column-pandas-dataframe-based-on-if-else-condition/

https://www.data-science-architect.de/bedingte-berechnungen-pandas/


###Day of Week

https://pandas.pydata.org/docs/reference/api/pandas.DatetimeIndex.dayofweek.html


### Outliers

https://knowledge.udacity.com/questions/268185


### Violin plot

https://stackoverflow.com/questions/60131839/violin-plot-troubles-in-python-on-log-scale


### Multivariate plot

https://knowledge.udacity.com/questions/618363


### Polishing Plots

https://knowledge.udacity.com/questions/550915

https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.rename.html

https://seaborn.pydata.org/generated/seaborn.scatterplot.html

https://knowledge.udacity.com/questions/401134


### Create Slides Deck

https://knowledge.udacity.com/questions/357457


### Re-Submission

Review #1

Include at least one function to replace repetitive code

def myHistPlot(df, xVar, bins = None):
    
    # plot
    
    df[xVar].hist(bins = bins,
                  rwidth = 0.7,
                 figsize = [20, 5],
                 grid = False)
    
    # title
    
    plt.title(f'Distribution of {xVar}'.title(),
             fontsize = 14,
             weight = 'bold')
    
    # x axis
    
    plt.xlabel(xVar.title(),
              fontsize = 10,
              weight = 'bold')
    
    # y axis
    
    plt.ylabel('Frequency'.title(),
              fontsize = 10,
              weight = 'bold')