# Document Image Features #

The following two features can be extracted quickly. They are all scalable and "fused" into a high-dimension vector for each image.


## Projection Histogram Feature ##

Here is the input image:

![http://farm6.static.flickr.com/5274/5913891843_dd17454e12.jpg](http://farm6.static.flickr.com/5274/5913891843_dd17454e12.jpg)

Calculate the projection histogram:

![http://farm6.static.flickr.com/5277/5914452922_8890caa6b4.jpg](http://farm6.static.flickr.com/5277/5914452922_8890caa6b4.jpg)

After partition and normalization, the projection histogram feature is described as 50-dimension (configurable) vector:

{60, 61, 17, 53, 59, 59, 59, 59, 59, 59, 59, 59, 59, 59, 59, 59, 59, 58, 57, 59, 59, 59, 59, 59, 38, 20, 68, 29, 100, 83, 61, 10, 15, 81, 61, 20, 49, 82, 44, 4, 22, 25, 57, 37, 10, 0, 0, 0, 96, 32}

## Density Distribution Feature ##

![http://farm6.static.flickr.com/5318/5914192115_40725f2bc7.jpg](http://farm6.static.flickr.com/5318/5914192115_40725f2bc7.jpg)

The density distribution feature is described as 120-dimension (configurable) vector:

{57, 59, 66, 76, 69, 59, 40, 40, 40, 26, 18, 18, 0, 0, 42, 100, 100, 100, 100, 100, 100, 39, 0, 0, 0, 0, 42, 100, 100, 100, 100, 100, 100, 39, 0, 0, 0, 0, 42, 100, 100, 100, 100, 100, 93, 38, 0, 0, 0, 0, 41, 100, 100, 100, 100, 100, 100, 38, 0, 0, 62, 65, 64, 65, 66, 66, 67, 63, 25, 19, 18, 18, 66, 77, 52, 45, 46, 47, 47, 47, 44, 43, 42, 42, 26, 93, 87, 68, 54, 39, 28, 29, 29, 27, 24, 1, 64, 82, 70, 50, 43, 25, 26, 0, 0, 0, 0, 0, 25, 18, 18, 18, 19, 18, 18, 25, 35, 33, 34, 34}