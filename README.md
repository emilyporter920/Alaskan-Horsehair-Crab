# Alaskan Horsehair Crab Analysis

## Overview
This dataset was pulled from Kaggle and contains data collected from 1980 to 2018. The image below shows the specific data that was collected.

<p align="center">
    <img
         src=Resources/Crab_data_df.png
         >
    </p>

## Analysis

### Figure 1

**The first figure was created to show the distribution of crabs over the years. This figure allows the user to interact with the data via a scroller that allows them to view through all of the years of data.**

<p align="center">
    <img
         src=Resources/Distribution_scatter_horsehair_crab.png
         >
    </p>

-----
### Figure 2
    
**The second figure was created to show the distribution of male horsehair crabs based on latitude and longitude.**

<p align="center">
    <img
         src=Resources/Male_horsehair_crab_density.png
         >
    </p>
    
-----
### Figure 3

**The third figure was created to show the distribution of female horsehair crabs based on latitude and longitude.**

<p align="center">
    <img
         src=Resources/Female_horsehair_crab_density.png
         >
    </p>
    
-----
### Figure 4

**The fourth figure was created to show the total horsehair crab density based on latitude and longitude.**

<p align="center">
    <img
         src=Resources/Total_horsehair_crab_density.png
         >
    </p>
    
-----
### Figure 5

**The fifth figure was created to show the horsehair crab's CPUE, catch per unit effort, between 1980 and 2018.**

<p align="center">
    <img
         src=Resources/Horsehair_crab_cpue_by_year.png
         >
    </p>

-----
### Example of Code
**Below shows an example of code for creating Figure 1**

```
# Create a figure that shows distribution of crabs over the years
figmap = px.scatter_geo(crab_data_df, lat='latitude', lon='longitude',
                       color='maturity', size='cpue', hover_name='name',
                       hover_data=['bottom_depth', 'surface_temperature', 'bottom_temperature'],
                       animation_frame='year', color_discrete_map={'Total male':'#00bc06', 
                                                                   'Total female':'#9b00e0'},
                       width=950, height=650, projection='aitoff')

figmap.update_geos(resolution=50, fitbounds='locations', framecolor='#FFFFFF',
                  showland=True, landcolor='#226d00',
                  showocean=True, oceancolor='#000000',
                  showlakes=True, lakecolor='#005AA8',
                  showsubunits=True, subunitcolor='#000000')

figmap.update_layout(template='plotly_dark')

figmap.show()
```

-----
## Summary
**Figure 1:**
* Shows the drastic decrease in number of horsehair crabs from 1980 until 1990. After 1990 there appears to be another drastic decrease in the number of horsehair crabs with an uptick taking place in 2010 and slowly tapering off since.

**Figure 2:** 
* Shows that male horsehair crabs have a broad range with large amounts between -170 and -160 longitude and between 56 and 60 latitude.

**Figure 3:** 
* Shows that female horsehair crabs have a more distinct range with large amounts mainly found between -171 and -167 longitude and between 57 latitude and 60 latitude.

**Figure 4:** 
* Shows the total horsehair crab density based on longitude and latitude with a large amount found between -172 and -167 longitude and between 56 and 59 latitude.

**Figure 5:** 
* Shows the drastic decrease after 1980, with an uptick found in 1990 which slowly goes back down until reaching an all time low in 2004. Another uptick occurs in 2010 with the largest CPUE per year since 1980 occuring in 2013 which then decreases. 
     
**It appears that each uptick in CPUE occurs approximately every decade. This might be due to the generation of young crabs evading large fish netting until they are old enough to be caught and sold. Afterall, small crab isn't as profitable as large crab.**
