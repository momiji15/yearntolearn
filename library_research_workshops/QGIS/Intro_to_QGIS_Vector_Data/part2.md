# Introduction to QGIS - Vector Data: Part 2

## Units
### Unit 1: Basic Cartographic Elements
### Unit 2: Symbolizing Layers
### Unit 3: Creating and Exporting a Map Layout

## Unit 1: Basic Cartographic Elements
### Unit Objectives
1. Identify basic cartographic elements of a map.
2. Identify symbolization considerations for symbolizing quantitative data.

Before we get into map making, it's important to understand basic cartographic elements of a map. 


## Unit 2: Symbolizing Layers
### Unit Objectives
1. Selecting an appropriate color scheme for polygon data.
2. Producing a symbology by size for points data.

### Terms to Know:
- chloropleth map: A map in which color is used to represent value over a specific area. 
- color hue: Refers to different colors, such as blue and green.
- color value: Refers to different shades of one hue such as dark blue and light green. Colors become darker by adding
  black to the hye, and colors become lighter by adding white to the hue.
- color intensity: Also known as saturation. This is the brightness of the color. Adding colors can make the hue less
  intense. For exmaple, adding grey to a hue can make it less intense. If you are having issues differientating value from 
  intensity, you can think of intensity as how different or similar a color is from grey.
- ordinal data: Data that has an order to it. 
-


#### Lesson 1: Selecting an Appropriate Color Scheme for Polygon Data
Using what we learned in the previous lesson, lets add some symbolization to our point and polygon data. Our final product will be a chloropleth map which shows the relationshop of the student to teacher ratio to the number of individuals in block groups who have an income to poverty ratio over two.  Let's start first with the polygon data. 

1. Right-click on **stl_bg** and click on **Properties**.

2. In the left-hand panel, click on **Symbology**.

3. On the top of the Layer Properties window you will see a drop-down menu in which **Single symbol** is the default. Click on it and choose the **Graduated** option.

4. For **Value**, choose **pct_gt_2** from the drop-down menu.

5. You can leave the **Color Ramp** to the default color of **Reds** for now.

6. Click on the **Classify** button and you will see the data classified into five groups.
![](Pictures/pt2unit1_1.png)

Take a closer look at the options of **Mode** towards the bottom of the Layer Properties window. You can classify your data in various ways which can be dependent on the distribution of the data, number of values, and the overall goal of the map. Here are some of the common classification schemes:

- [quantile scheme](http://wiki.gis.com/wiki/index.php/Quantile): When each class has the same number of data values. This scheme is recommended for ordinal data like values from a Likert Scale. While the advantage of this scheme is that there is an equal number of values in each class, the disadvantage is that dissimilar values might be put in the same class.

- [equal interval](http://wiki.gis.com/wiki/index.php/Classification) scheme: When each class is broken in regular intervals(for example, 10-20, 20-30, etc). The advantage of this scheme is that this scheme is great to use when comparing a series of maps, but the disadvantage of this scheme is that it does not take in consideration the distribution of the data.

- [natural breaks scheme](http://wiki.gis.com/wiki/index.php/Jenks_Natural_Breaks_Classification): A classification scheme that takes in consideration the distribution of data. This results in classes in which the differences in values are minimized. Class breaks are based on breaks in the data. The advantage of this scheme is that it takes in consideration the data distribution, but using this scheme isn't recommended for data with a low amount of variation.

7. Let's take a look at the distribution of data. Click on the **Histogram** tab, which is located under **Color Ramp**. 
![](Pictures/pt2unit1_2.png)

The data is close to a normal distribution. Let's choose **natural breaks** as the classification scheme.

8. Click on the **Classes** tab and in the drop-down menu for **Mode**, choose **Natural Breaks(Jenks)** and click **OK**. You will now see the block group polygons classified by color. The darker color signifies block groups with a high number of individuals who have an income to poverty ratio over two. 

9. Make sure to save your document.

#### Lesson 2: Producing a Symbology by Size for Points Data
Now we're going to adjust the symbology of the points data to adjust the size of the points by the student teacher ratio(**ST_ratio**).

1. Right-click on **stl_schools** and click on **Properties**.

2. In the left-hand panel, click on **Symbology**.

3. On the top of the Layer Properties window you will see a drop-down menu in which **Single symbol** is the default. Click on it and choose the **Graduated** option. 

4. Let's change the color and size of the points. Click on the down arrow button in **Symbol** and choose a yellow color for your points. Under **Method** choose **Size**.

5. Click **Classify** on the bottom of the Layer Properties window. Keep the classification to **Natural Breaks (Jenks)** then click OK. Notice how the points data changed. Which parts of St. Louis has a high student to teacher ratio and a low student teacher ratio?

![](Pictures/pt2unit1_3.png)

6. Make sure to save your document.


### Unit 3: Creating and Exporting a Map Layout
1. Generate a print layout for a map.
2. Create a map incorporating the basic cartographic elements.
3. Export a map in an appropriate file format.

#### Lesson 1: Generate a Print Layout for a Map

Now that we have symbology for all of our layers, it's time to create a map! 

1. Click on **Project > New Print Layout**.

2. Give your layout a title. Let's call it **Student teacher Ratio by Block Group**. Click **OK**. Another window will open up. This is the map layout window. 

![](Pictures/pt2unit3_1.png)

3. Let's change our page to portrait orientation. Right-click anywhere within the page and click on **Page Properties...**. On the right-hand side of the print layout window, you will see an **Item Properties** panel. Under **Orientation** click on **Portrait**. The page layout will then turn to portrait orientation. 

Before we move on, it's good to be acquainted with some of the buttons in the left-hand toolbar:
Here are some useful buttons to know in the left toolbar: 

- **Select/Move item** ![](Pictures/pt2unit3_4.png): Moving the actual data frame.  
- **Move item content** ![](Pictures/pt2unit3_4.png): Moving the content within the data frame. 
- **Adds a new Map to the Layout** ![](Pictures/pt2unit3_2.png): Adds a Map to the page layout.

4. Let's add our Map to the map layout. On the left toolbar, click on the **Adds a new Map to the Layout** button.

Your pointer will turn into a cross. Left-click and drag a rectangle of appropriate size within your page layout. Make sure to leave enough room in your page for a **title** and **created by/data source** section, but make sure your rectangle is big enough to contain cartographic elements such as the **scale bar, north arrow, and legend**.

![](Pictures/pt2unit3_3.png).

 


