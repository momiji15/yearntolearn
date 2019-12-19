# Introduction to QGIS - Vector Data: Part 1

## Units
### Unit 1: Introduction to Vector Data
### Unit 2: Finding and Downloading GIS Data
### Unit 3: Prepare GIS Data in a QGIS Workspace
### Unit 4: Producing Basic Queries for Data Discovery
### Unit 5: Joining Tabular Data to Vector Data
### Unit 6: Computing values with Field Calculator

## Unit 1: Introduction to Vector Data
### Unit Objectives
  1. Define Geographic Information Systems (GIS) 
  2. Describe the two types of GIS data.
  3. List three types of GIS vector data.
  4. Describe the structure of GIS data.

### Terms to know
Geographic Information Systems(GIS): A computer system that is used to capture, display, and analyze data that has a spatial reference on Earth.

vector data: GIS data that represents data on the earth through points, lines, and polygons.

raster data: GIS data that represents data on the earth through a grid of pixels.

shapefile: A file format for vector data, which comprises of at least four different file types.

#### GIS, Vector and Raster GIS Data
Geographic Information Systems (GIS) is a very powerful tool when it comes to understanding physical and socio-cultural processes on the earth. There are various types of GIS software out there, however a common thread with the software is the data they deal with. GIS uses vector data and raster data to represent features on the earth. Vector data is made up of points, lines and polygons. An example of point data could be a points representing school locations (which you will see in today's workshop). An example of line data could be lines representing rivers and streams. Finally, an example of polygon data could be school districts.

On the other hand, raster data is a grid of pixels in which each value represents a feature on the earth. For example each pixel of a raster image of a forest profile could represent the type of tree in the forest. For today's workshop we will be exclusively focusing on vector data. The GIS software that we will be using today is Quantum GIS, also known as QGIS. QGIS is a very convenient software, for it is available for both Mac and Windows machines and it is free and open source. 

One of the file formats that represent vector data is a shapefile, which is actually made of up of various filetypes such as .shp, .shx, .dbf, .prj, and .xml. We will be working with shapefiles for this workshop. The reason that shapefiles are made up of various files is due to the nature of vector data. Vector data is not just visual in nature; a database underlies vector data which in which each point, line, and polygon is represented by a record in a database. In addition, a shapefile might contain metadata, which is data about data. In short, metadata gives you information about how the shapefile was derived.

![](Pictures/unit1_1.png)


## Unit 2: Finding and Downloading GIS Data
### Unit Objectives
1. Identifying relevant websites to download GIS data for an area of interest.
2. Use relevant websites to download GIS data.

### Terms to know
[Census block group](https://www2.census.gov/geo/pdfs/reference/GARM/Ch11GARM.pdf): The smallest geographic unit in which the Census unit collects census data. 

#### GIS Data Sources: Where to go?
As mentioned in the [introduction](https://github.com/momiji15/yearntolearn/blob/master/library_research_workshops/QGIS/Intro_to_QGIS_Vector_Data/intro_to_qgis_vector_intro.md
), our final project will be a map that displays schools in St. Louis city and shows the student to teacher ratio by census block group. So the GIS data we will need are as follows:
1. public schools in St. Louis city.
2. Census block group data for St. city.

So where do we start? Let's work our way down this short list.

##### Schools data
[The Missouri Spatial Data Information Service(MSDIS](http://msdis.missouri.edu/) has a variety of spatial data over the state of Missouri, including our schools data.

1. Go to the MSDIS website.
2. Under the **Download Data** dropdown menu, click on **Data Portal**. 
3. Scroll down on the site and click on the **Education** icon.


