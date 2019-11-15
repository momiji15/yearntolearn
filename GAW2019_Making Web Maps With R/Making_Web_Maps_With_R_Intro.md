---
title: "Making Web Maps Using R Introduction"
output: html_notebook
---
```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## Workshop purpose
The purpose of this workshop is to make and publish a web map using Leaflet for R. [Leaflet](https://leafletjs.com/) is a javascript library which allows you to make web maps. There is a leaflet package in R which allows you create your own Leaflet map within an R programming environment. 

By the end of this workshop, participants will be able to:

  1. Map point data in leaflet.
  2. Download polygons that contain demographic information by using the tidycensus package.
  3. Map polygon data in leaflet.
  4. Embed a map in an interactive document using R Markdown.
  5. Publish a your RMarkdown document with the map in RPubs.
  
## Final Product
By the end of this workshop, you will have created a Leaflet map embedded in an R Markdown document. Here is an [example](https://rpubs.com/ds_workshops/534926) to refer to.

## Difficulty
It is preferred that participants have basic familiarity with R and the RStudio. If you are completely new to R, then you should be able to follow along. Whether you're a complete beginner to R or experienced in R, but not familiar with using Leaflet, don't be shy and make sure that you ask a question if you have one or 
let me know if you are lost! In addition, it is preferred that you have a basic idea of vector data for mapping (points, lines, and polygons).

## Slides
You can access the slides for this workshop [here](https://momiji15.github.io/wustl_rwebmap/WMWR2019.html).

## Set-up

### R and RStudio
If you are using the Instruction Lab computers, then R and RStudio has already been installed. If you are using your own computer, then follow the steps under the [Getting Started](https://www.r-project.org/) section on the R Project page. After installing R you are able to install [R Studio](https://www.rstudio.com/products/rstudio/download/). Make sure to download the free version of 
R Studio!

### R Pubs Account
There are many ways in which you can deploy your map online. One simple way to do this is through RPubs which is a free service which hosts R Markdown documents. Before you can use RPubs, you will have to create an [account](https://rpubs.com/users/new).

### Required Packages
You will need to install these packages in order to do this workshop. The descriptions of these packages
is not exhaustive; further information, refer to the links provided for each package. Any further packages
that is needed 

- [leaflet:](http://rstudio.github.io/leaflet/) This package allows you to utilize Leaflet, which uses JavaScript, within an R environment.
- [tidycensus:](https://walkerke.github.io/tidycensus/) This package allows you to do a specialized search download census data. In addition, youcan download polygons of a pre-defined administrative boundary (state, county, census tract) which includes the census data.
- [tidyverse:](https://www.tidyverse.org/) This package is actually suite of packaages that allows you to easily manipulate your data.
- [rgdal:](https://cran.r-project.org/web/packages/rgdal/rgdal.pdf) This package will allow you to load shapefiles into RStudio.
- [sf](https://r-spatial.github.io/sf/articles/sf1.html) This package allows you to store features, such as polygons, as R objects.
- [rmarkdown:](https://rmarkdown.rstudio.com/) This packaage allows you to make dynamic documents which can be shared in various formats and published onlines.
- [magrittr](https://magrittr.tidyverse.org/) This package allows you to use pipe operators which will 
allow you to better streamline your workflow.

In order to install and load the packages, please type the following code in your .R file.

```{r, eval = FALSE}
install.packages("leaflet")
install.packages("tidycensus")
install.packages("tidyverse")
install.packages("rgdal")
install.packages("sf")
install.packages("rmarkdown")
install.packages("magrittr")

library(leaflet)
library(tidycensus)
library(tidyverse)
library(rgdal)
library(sf)
library(rmarkdown)
library(magrittr)
```

### Census API Key
You will have to register for a US Census Bureau API key which allows you to download Census data using tidycensus. You can download the key [here](https://api.census.gov/data/key_signup.html).

### Points Data
- [*LTC_Facilities.shp: Long Term Facilities in St. Louis City.*](https://wustl.box.com/s/ge36cnzd4wwdqeklmjqejoq9pkrrqhnt)

This data was downloaded from the [Missouri Spatial Data Information Service](http://msdis.missouri.edu/). You will need to download points data from the link provided. This data has been prepped for the tutorial. This data is important to note when you download data, it is not ready to go and you will have to do some data manipulation before using it!


### For Further Information
We will not be able to cover everything in this tutorial. If you want to learn how to further customize your map, refer to the [Leaflet for R](https://ugoproto.github.io/ugo_r_doc/pdf/leaflet-cheat-sheet.pdf) and [R Markdown](https://rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf) cheatsheets.
