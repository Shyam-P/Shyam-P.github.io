---
title       : Explore Data Frame
subtitle    : Shiny App
author      : P. Shyamasunder
job         : Course Project created on Tue Jun 24 03:27:27 2014
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [shiny]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides


---

## Web interface to 'browse' a data frame

1. Query data frame or any of its variables

2. Visualize various types of plots

3. Filter(subset) input data frame as needed to explore


--- .class #id 

## Query Element

1. Choose to query the entire data frame or any of its variables

    Select option from drop down list in sidebar panel

2. Key information is updated in the text window in main panel

    Output includes str(), summary(), class of selected variable, etc
    
3. Choosing 'None' (default) causes the text window to show 1 line message

    useful to 'collapse' the text window to a single line while plotting

--- .class #id 

## Visualize Plots

1. Use can choose 3 variables for plotting: Y, X and By

    The 'By' is used to group plot data 
    (example: facets in ggplot or boxplot with a factor variable)

2. Plots dynamically change type based on selection

    Selecting only Y variable gives a histogram, Y with By variable shows a 
    boxplot with grouping. Y with X shows a scatter plot.
    
3. Run statistical functions (where appropriate) to summarize data 

    Useful to 'sum' or 'mean' large datasets to understand high level trends
    For example, viewing 'Total Emissions' rather than "Emissions' vs year.
    The Total Emissions plot provides more meaning than the scatter plot.
    Choose from "None", "Sum" or "Mean" options

--- .class #id 

## Filter Data

1. Clean Data

    Use filters to clean NA records: either for data frame or specific variable

2. Select data rows pertaining to a large set of logical filters

    Based on the query information, user can specify filters to drop outliers.
    Or select specific values such as a state code(s)/year(s) for evaluation.
    User can also search for specific strings/names within a variable with ease
    (%in% operator in filter specification uses grepl() output to subset)
    
    Any number of filters can be input: are applied sequentially to dataframe.
    Final reduced data frame is input to query and plot commands.    
    
3. Feedback on filters input by user

    Filters are processed and feedback on list of filters that are valid and 
    invalid is provided so user can take corrective action on input errors.
    
    Text & plots are updated with reduced data set for valid filters.
    
