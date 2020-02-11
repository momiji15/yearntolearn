# Introduction to QGIS - Vector Data: Part 1

There are two classifications of data in GIS; vector data and raster data. This workshop will focus on becoming familiar with vector data.  The main objectives to part one is to identify websites that have geospatial data, downloading geospatial data, and manipulating data with QGIS. 

## Units
### Unit 1: Introduction to Vector Data
### Unit 2: Finding and Downloading GIS Data
### Unit 3: Prepare GIS Data in a QGIS Workspace
### Unit 4: Producing Basic Queries 
### Unit 5: Joining Tabular Data to Vector Data
### Unit 6: Computing values with Field Calculator

## Unit 1: Introduction to Vector Data
### Unit Objectives
  1. Define Geographic Information Systems (GIS). 
  2. Describe the two types of GIS data.
  3. List three types of GIS vector data.
  4. Describe the structure of GIS data.

### Terms to know
- Geographic Information Systems(GIS): A computer system that is used to capture, display, and analyze data that has a spatial reference on Earth.

- vector data: GIS data that represents data on the earth through points, lines, and polygons.

- raster data: GIS data that represents data on the earth through a grid of pixels.

- shapefile: A file format for vector data, which comprises of at least four different file types.

#### GIS, Vector and Raster GIS Data
Geographic Information Systems (GIS) is a very powerful tool when it comes to understanding physical and socio-cultural processes on the earth. There are various types of GIS software out there, however a common thread with the software is the data they deal with. GIS uses vector data and raster data to represent features on the earth. Vector data is made up of points, lines and polygons. An example of point data could be a points representing school locations (which you will see in today's workshop). An example of line data could be lines representing rivers and streams. Finally, an example of polygon data could be school districts.

On the other hand, raster data is a grid of pixels in which each value represents a feature on the earth. For example, each pixel of a raster image of a forest profile could represent the type of tree in the forest. For today's workshop we will be exclusively focusing on vector data. The GIS software that we will be using today is Quantum GIS, also known as QGIS. QGIS is a very convenient software, for it is available for both Mac and Windows machines and it is free and open source. 

One of the file formats that represent vector data is a shapefile, which is actually made of up of various filetypes such as .shp, .shx, .dbf, .prj, and .xml. We will be working with shapefiles for this workshop. The reason that shapefiles are made up of various files is due to the nature of vector data. Vector data is not just visual in nature; a database underlies vector data which in which each point, line, and polygon is represented by a record in a database. In addition, a shapefile might contain metadata, which is data about data. In short, metadata gives you information about how the shapefile was derived.

![](Pictures/unit1_1.png)


## Unit 2: Finding and Downloading GIS Data
### Unit Objectives
1. Identifying relevant websites to download GIS data for an area of interest.
2. Use relevant websites to download GIS data.

### Terms to know
- [Census block group](https://www2.census.gov/geo/pdfs/reference/GARM/Ch11GARM.pdf): The smallest geographic unit in which the Census unit collects census data. 
- [TIGER Lines](https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html): Geographic features for all 50 states from the  *Topographically Integrated Geographic Encoding and Referencing* database(thus the acronym TIGER). Examples of TIGER line products are rivers, roads, and administrative boundaries such as counties.

#### GIS Data Sources: Where to go?
As mentioned in the [introduction](https://github.com/momiji15/yearntolearn/blob/master/library_research_workshops/QGIS/Intro_to_QGIS_Vector_Data/intro_to_qgis_vector_intro.md
), our final project will be a map that displays schools in St. Louis city and shows the student to teacher ratio by census block group. So the GIS data we will need are as follows:
1. public schools in St. Louis city.
2. Census block group data for St. Louis city.

So where do we start? Let's work our way down this short list.

##### Schools data
[The Missouri Spatial Data Information Service(MSDIS)](http://msdis.missouri.edu/) has a variety of spatial data over the state of Missouri, including our schools data.
![](Pictures/unit2_1.png)

1. Go to the MSDIS website.
2. Under the **Download Data** dropdown menu, click on **Data Portal**. 
3. Scroll down on the site and click on the **Education** icon.

![](Pictures/unit2_2.png)

4. You will see three results. Scroll down and you will see **MO 2019 Public Schools**. Click on the text and you will be directed to a page that shows you a preview of the data along with the various attributes of the data. On the right side of the page, click on the **Download** button which will display a drop-down menu. Click on shapefile and the file will automatically download. 

5. Before we move the data from the Downloads folder, we need to make a folder on your Desktop to store your GIS data. File management is essential to GIS and it is important to implement sound data management skills for GIS project management. You will learn such skills throughout this workshop. Create a folder and name it **GIS_Data**. It is important to not use spaces in naming your folders and files due to readability issues that could occur later on. Make sure to use an underscore in place of a space to prevent any problems down the road. Also, notice that **MO_2019_Public_Schools** also use underscores in place of spaces in the zipped file.

6. After creating your folder, move the **MO_2019_Public_Schools** shapefile to your **GIS_Data** folder.

##### Census Tracts

You will need to get the census tract shapefile for Missouri along with the pertinent demographic information we want per census tract. TLet's first get the census tract informaton. 

1. Go to the [US Census Bureau TIGER/Line](https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html) website and under **2019**, click **Web Interface**. Keep **2019** selected for **Year** and select **Block Groups** in the **Select a layer type** section. Press **Submit** when you're done.

2. Under **Select a State**, select **Missouri**, and click **Download**. Move the downloaded folder to your **GIS_Data** folder. Rename the folder of your block groups to **MO_Block_Group_2019*.

3. Unzip your downloaded files. If you are using a Mac, you can just double-click on the zipped folder and it will unzip.
If you are using Windows, you will **right-click > Extract All**.

##### Tabular Data
The demographic information that we need is stored in a table in **.csv** format. You can get census data through the [Census' data portal](data.census.gov).

1. Go to the Census data portal website.

2. Click on **Advanced Search**.

3. Click on **Geography >** **Block Group**(under Geography)**> Missouri**(under Within State) **> St. Louis City**(under Within County)**>All Block Groups within St. Louis city,Missouri**(under St. Louis City, Missouri). On the bottom of the page, you should see a **Selected Filters** bar and **All Block Groups within St. Louis city, Missouri** should be displayed. 

4. Now click on **Topics** > **Income and Poverty**(Under Topics) **Income and Earnings >**(Under Income and Poverty) **Income and Earnings**. Click **Search** in the **Selected Filters** bar to view the filtered tables. 

5. Scroll down until you see **MEDIAN HOUSEHOLD IN THE PAST 12 MONTHS(IN 2018 INFLATION-ADJUSTED DOLLARS)** and click on it. This should be Table B19013. 

6. You should see a preview of the table. Press **Download** on the left-hand panel of the page. Click on the checkbox next to the **MEDIAN HOUSEHOLD IN THE PAST 12 MONTHS(IN 2018 INFLATION-ADJUSTED DOLLARS)** table and click on **Download Selected**. 
![](Pictures/unit2_4e.png)

7. Keep the defaults in the **Download** section. Everything should look like the image below. click **Download**. 
![](Pictures/unit2_5f.png) Once your files finished preparing, click **Download Now**.

8. Move your downloaded data to your **GIS_Data** folder. Rename the folder **STL_Income** and unzip the folder.


## Unit 3: Prepare GIS Data in a QGIS Workspace

### Unit Objectives
1. Adding vector data to a QGIS workspace.
2. Adding a csv file to a QGIS workspace.
3. Adding projections to your vector data.

### Terms to Know
- projection: A mathematical function that transforms the earth's 3D surface on a 2D surface.
Now that you have unzipped your data, it is not ready to put your shapefiles in a QGIS workspace.

1. Open up QGIS.

2. On the top menu bar, go to **File > New** to open a new workspace. You can also click on the left-most icon that looks like a blank sheet of paper to open a new workspace.

![](Pictures/unit3_1e.png)

3. Now, you will add the Missouri public schools and census block group shapefiles to your workspace. Press the **Open Data Source Manager** button which is below the **New Project** button.

![](Pictures/unit3_2e.png)

4. We are going to a add the Census block groups first. Click on the **...** under **Source and Vector Dataset(s)** and navigate back to your GIS_Data folder and then navigate to the  **MO_Block_Group_2019 folder > and then select **tl_2019-29_BG.shp**, and click **Add**. In the Data Source Manager, click **Add**.

5. We are going to add the schools next. Make sure that **Vector** is highlighted on the left menu panel on the **Data Source Manager**. Under **Source > Vector Dataset(s)**, click  **...** and navigate to the location of your shapefiles which should be in the **GIS_Data** folder. Navigate to the **MO_2019_Public_Schools** folder, click on **MO_2019_Public_Schools.shp**, and click **Open**.  In the Data Source Manager, click **Add**.

6. Go to **Project > Save** and save your project as **stl_schools**.

![](Pictures/unit3_3e.png)

7. Your workspace should look similar to this. Don't be concerned about the colors of the shapefiles in your workspace being different than what you see here. 


8. We need to add a projection to our project. At times, you can easily tell that the data is not projected for the boundaries look distorted and the edges of the boundaries are straight lines. To project our data, we will export each shapefile and create a new layer with our new projection.

9. On the bottom right-hand corner of the QGIS project window, you will see a button that says **EPSG: 4326**. Click the button.
![](Pictures/unit3_5g.png)

10.  This will display the **Project Coordinate Reference System (CRS)** window. In **Filters**, type **102696**. Under **Coordinate Reference Systems of the World** should see **NAD_1983_StatePlane_Missouri_East_FIPS_2401_Feet** which you can confirm for the EPSG is indeed **102696**. Click on the coordinate system and then click **OK**. 
![](Pictures/unit3_6.png)

As you can see, the shapefiles have changed and are no longer distorted. You can also see that the projection of the QGIS project is in the correct projection indicated by the **EPSG: 102696** in the bottom right-hand corner. Save your project.
![](Pictures/unit3_7e.png)

This projection was on-the-fly; while the project's projection changed, the shapefiles projection is not the same as the project's projection. Let's change that.

11. Let's first project the **MO_2019_Public_Schools** shapefile. Right-click on the shapefile and click **Export > Save Features As**.

12. Keep the **Format** as an **ESRI Shapefile**. Click the **...** next to the text box under **File Name**, navigate to your **GIS_Data** folder and then **MO_2019_Public_Schools** folder. Name your new layer **MO_2019_Public_Schools_Project**. 

13. Click the **Select CRS** button in **CRS**. Under **Filter**, type **Missouri** to get to the projection that we need. Under **Coordinate Reference Systems of the World**, highlight **NAD_1983_StatePlane_Missouri_East_FIPS_2401_Feet**. Click **OK**.

![](Pictures/unit3_8.png)

14. Click **OK** in the **Save Vector Layer as...** dialogue box. You will see your newly created shapefile in the Layers section.

15. Now we will do the same with the Missouri census tracts. Right-click on the shapefile and click **Export > Save Features As**.

16. As with **MO_2019_Public_Schools**, you will keep the format to **ESRI Shapefile**. Navigate to your **GIS_Data** folder and then to  **MO_Block_Group_2019**. Name your new layer **MO_Block_Group_2019_Project**.

17. Click the **Select CRS** button in **CRS**.

18. Under **Recently Used Coordinate Systems**, you should see the projection that you just used. Click on **NAD_1983_StatePlane_Missouri_East_FIPS_2401_Feet** and click on **OK** and then **OK** in the **Save Vector Layer as...** dialogue box. Your newly created layer will show up in the Project window and under the Layers panel. 
![](Pictures/unit3_9e.png)

19. In the **Layers** panel, uncheck **MO_2019_Public_Schools** and **tl_2019_29_bg**. Right-click on each of these files and click **Remove Layer**. Save your project.

Congratulations! You just finished importing all the data you need into QGIS.


## Unit 4: Producing Basic Queries

### Unit Objectives
1. Produce a *select features by expression* query.
2. Produce a *select features by location* query.

### Terms to know
- FIPS code: A numbers which uniquely identifies a geographic unit such as a county or state. FIPS stands for *Federal Information Processing Standard*. State level FIPS codes have two digits while county level FIPS codes have five digits in which the first two digits are the state FIPS code. 

With QGIS, you can select features either by expression or by location. When you select features by expression, you are selecting a features of vector data based on a particular attribute such as all of the census block groups in a specific county. When you select features by location, you can select features of vector data based on their location, such as selecting all the cenus block groups that are contained within a St. Louis City polygon. Let's give both a try.

#### Producing a select features by expression query 
1. Right-click on **MO_Block_Group_2019_Project** and click on **Open Attribute Table**.

2. As you can see, a database underlies this polygon dataset in which there are records for each feature contained in the s
   dataset. You can see this by clicking on the number for the first record and right-click the value that is in 
   **STATEFP**. Then click on **Zoom to Feature** which zooms into the feature and highlights it as well. 
3. To zoom out to see the entire Missouri block groups, click on the **Zoom to Layer** button in the QGIS toolbar.


4. Let's select the census block groups that are in St. Louis City by using an expression. There are two ways you can do 
   this: 
   Option 1: Open the attribute table and click on the **Select features using an expression** button that is on the 
   the attribute table toolbar.
   ![](Pictures/unit4_2.png)    
   Option 2: Click on the **Select by Expression** button on the QGIS toolbar.
   ![](Pictures/unit4_3.png)
   
5. Using either option in #4, click on **Select by Expression**. We will be selecting St. Louis City block groups by County FIPS codes which is listed as **COUNTYFP** in the attribute table. Since St. Louis City is its own administrative unit separate from St. Louis county, it has it's own FIPS code which is **510**.
   ![](Pictures/unit4_4.png)
 
6. Let's create the query. In the middle box, click on **Fields and Values** and double-click **COUNTYFP**. You should see `COUNTYFP`appear in the Expression box on the left.

7. Click on the `=` button located in the toolbar above the Expression box. You should see `=` appear in the Expression box.

8. In the right box under **Values**, click on **All Unique** which will show all of the values that are in the **COUNTYFP** field. Scroll down until you find **510** and double-click on it. Your expression should look like this:


9. Click **Select Features** and 360 features should be selected. Click **Close** to close the Expression box. You might not see the selected features, so click on the **Zoom to Selection** button which is to the left of the **Zoom to Layer** button. You should see all of the city of St. Louis selected.

10. We're going to export those selected block groups which will result in creating a new shapefile. Right-click on **MO_blck_group_2017_Project** > **Save Selected Features As...**

11. Keep the **Format** as an **ESRI Shapefile** and for **File name**, click on the ellipses(...) and navigate to your GIS_Data folder. Create a new folder called **stl_bg** and navigate to your folder. You will save your shapefile here. Give your shapefile the same name as the folder that you just created. Make sure that the **CRS** is the **Project CRS: EPSG 102696 - NAD_1983_StatePlane_Missouri_East_FIPS_2401_Feet**. Keep everything else the same and press **OK**. 
![](Pictures/unit4_5.png)
*Note that the file extensions will be different for you than what you see in the picture above*

12. Your newly created shapefile is added to the layers panel. Save your QGIS project.

#### Producing a select by location query
Now that we have the St. Louis City census tracts, we can use it as a "cookie cutter" of sorts and select schools that are in St. Louis City. We can do this by producing a select by location query. 

1. In the QGIS menu bar, click on **Vector** > **Research Tools** > **Select by Location**.

2. Under the drop-down menu in **Select features from**, choose **MO_2019_Public_Schools_Project**. Under **Where the features(geometric predicate)**, only check the box for **intersect**. Under **By comparing to the features from**, choose **stl_bg** from the drop-down menu. Finally, under **Modify current selection by**, make sure **creating new selection** is selected. Click **Run** to run the query. All of the schools within stl_bg should be selected.
![](Pictures/unit4_6.png)

3. As we did previously, we will export the selected features into a new shapefile. Right-click on **MO_2019_Public_Schools_Project** and click **Export** > **Save Selected Features As...**. 

4.Keep the format as **ESRI Shapefile** and make sure to set the CRS to Missouri State Plane East.  For the **file name**, make sure to navigate to the **GIS_Data** folder, create a new folder called **stl_schools** and save your shapefile with the same name in that folder. Press **OK** and you should see **stl_schools** under the Layers pane in your QGIS project.  Save your project.


## Unit 5: Joining Tablular Data to Vector Data
### Unit objectives
1. Identify key fields fields between two different datasets.
2. Generate formatted key fields.
3. Generate a join between a csv file and a shapefile.

### Terms to know
- key: a field that is common to two different datasets.
- metadata: data about data. It gives you information about the data source.

Our shapefile of St. Louis block groups does not have any socio-economic data attached to it. We can join the .csv file that we downloaded from NHGIS based on a field that is common to both data, which is called a key. The key that we will use to join the .csv file to the shapefile is **GISJOIN**. 

1. Go into your GIS_Data folder and unzip **STL_Income**. In the **STL_Income** folder, you will see three files:
  - **ACSDT5Y2018.B19013_data_with_overlays_...csv**: Shows the median income per census block group.
  - **ACSDT5Y2018.B19013_metadata_....csv**: Gives the metadata information about the csv file such as the column names.
  - **ACSDT5Y2018.B19013_table_title_...txt**: Gives information about the data table downloaded. 

2. Let's add the csv file to our project. Click on the **Open Data Source Manager** button and on the left-hand panel, click on **Delimited Text**. 

2. Click on the **...** button next to File Name and navigate to **GIS_Data > STL_Income > ACSDT5Y2018.B19013_data_with_overlays_...csv**. 

3. Let's give our csv file a more simplified name when it displays in QGIS. In the **Layer name** type **stl_income_bg_table**. Keep the rest of the defaults and click **Add** then **Close**. You will see **stl_income_bg_table** in the Layers panel.

  ![](Pictures/unit5_1.png)
  
  
  ![](Pictures/unit5_2.png)


4. We are now going to join **stl_bg_table** to **stl_bg**. The way that tabular data is able to be joined to the polygons is through joining them by a field that is located in both attribute tables. This common field is known as a **key**. Let's see which field is both common in both data sources. Right-click on **stl_income_bg_table** and click on **Open Attribute Table**. Do the same for **stl_bg**. From looking at both datasets, **GEOID** might be the common field in these datasets. Or is it?

#### Generating formatted key fields

5. At second glance, there is a difference between the **GEOID** field in **stl_income_bg_table** and **stl_bg**. **stl_income_bg_table** has **1500000US** listed before the series of numbers. To properly join the data, we need to do a data transformation in which we have a field that lists the numbers after the above mentioned code. We are going to extract the numbers after this code through the right() function. You will need to enter the **right("GEOID", 12)** in the field calculator which will get all the characters twelve characters from the right of GEOID.

6. In the **stl_income_bg_table** attribute table, click the **Open field calculator** button. In the **Output field name**, name this new field **GEOID2**. In the **Output field type**, select **Text(string)**. In the middle box, click on **String** and click on **right**. Click on **Fields and Values** and click on **GEOID**. Then type **, 12)**. Confirm that everything in expression box the field calculator looks like below.

![](Picture/unit5_3.png)

#### Generate a join between a csv file and a shapefile


5. Right-click **stl_bg** and click on **Properties...**. Click on **Joins** in the side panel of the Layer Properties window. Click the green plus button on the bottom to add a join to the polygon data.

6. In the **Add Vector Join** window, choose on **stl_bg_table**  from the drop-down menu as the **Join Layer**. For the **Join field** drop-down menu, choose **GEOID2** and for the **Target field** drop-down menu, chose **GEOID**. Check the the **Custom Field Name Prefix** box and remove the text that is in the text box. Click **OK**. 

![](Pictures/unit5_4.png)

----------------------------------------------------------------------------------------------------------------------------


You can see in the Layer Properties window that **stl_bg_table** was joined to **stl_bg**. Click **OK** to exit out of the Layer Properties window.

7. Right-click on **stl_bg** and click on **Open Attribute Table**. If you continue to scroll to the right, you will eventually see the joined fields. Don't be too concerned with any blank fields; the field you only need to concern yourself with is AHY1E001 which is the total population of people per Census block group and AH1JE008 which is the ratio of income to poverty level that is 2.00 and over. You can find out the meaning of each field by looking at the **codebook file(nhgisXXXX_ds233_20175_2017_blck_grp_codebook.txt)** that is located in **nhgisXXXX_csv**.

## Unit 6: Computing values with Field Calculator
### Unit Objectives

1. Produce field calculations with pre-existing fields.

With the field calculator, you are able to make new fields based on doing calculations with already existing fields. Let's perform a field calculation with the **stl_schools** and the **stl_bg** layers.  We're going to calculate the student and teacher ratio in the **stl_schools** layer and percentage of people in which the income to poverty ratio is over 2.00 in **stl_bg**. 

1. Right-click on **stl_schools** and click on **Open Attribute Table**. In the top attribute table toolbar, click on the **Open Field Calculator** button which will open the Field Calculator window. 

![](Pictures/unit6_1e.png)

2. In the Field Calculator window, make sure that the **Create a new field** box is checked. The **Output field** name should be **ST_Ratio**, the **Output field type** should be **Decimal number(real)** and the **Output field length** should be **10**. Under the **Expressions** box, you want to divide the **Teachers** field by the **Enrollment** field. In order to find the **Teachers** and **Enrollment** values, click on **Fields and Values** in the middle box in which you will see all of the fields in the attribute table. Once you confirmed these parameters, then click **OK**.

![](Pictures/unit6_2.png)

3. Right-click on the **stl_schools** layer and open the attribute table. If you scroll to the end of the attribute table, you should see **ST_Ratio**. Close the attribute table.

4. Let's calculate the percentage of people who have an income to poverty ratio of 2.0 and over by Census block group. Right-click on **stl_bg** and open the attribute table. Click on the **Open Field Calculator** button.

5. In the Field Calculator window, make sure that the **Create a new field** box is checked. The **Output field** should be **pct_gt_t2**. In the Field Calculator window, the **Output field type** should be **Decimal number(real)** and the **Output field length** should be **10**.

6. Let's create the expression. Open up the code book for your **nhgisXXXX_csv** file. The fields that we are going to be concerned with is **AH1JE008** which is the population of those who has a ratio of income to poverty level over 2 and **AH1JE001** which is the total population of the block groups. You're going ot divide **AH1JE008** by **AH1JE001**. Click on those fields in the **Fields and Values** section to make the expression. Once you confirmed these parameters, then click **OK**.
![](Pictures/unit6_3.png)

7. Confirm that your newly created field is in the attribute table by right-clicking on **stl_bg** and opening the attribute table.

8. If you want, feel free to do more field calculations to determine the percentage of population of individuals per block group with a specific income to poverty level ratio.

Now we have everything we need to create our map. Congratulations! You finished Part 1! Proceed to Part 2 to learn how to symbolize and design your map.











