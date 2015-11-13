This is a fast open source document image retrieval application. The document image feature is based on projection histogram feature and density distribution feature. The similarity is calculated by the Cosine similarity.

# Dependencies #
OpenCV 2.2 or later version

(Only core and imgproc modules are included, and highgui for load image.)


# Known Development Environment #
VS2005, VS2008, VS2010 express

# Document Image Features #
The following two features can be extracted quickly. They are all scalable and "fused" into a high-dimension vector for each image.

More details are in the wiki page:

http://code.google.com/p/opendir/wiki/OpenDIRImageFeatures

# Similarity #
In the default settings, cosine similarity between the vectors are calculated.
The project also includes Euclidean distance methods.

http://en.wikipedia.org/wiki/Cosine_similarity

# How to use #

OpenDIR:

> -w WRITEPATH: save features extracted from input images into WRITEPATH,
> if the WRITEPATH file already exists, it will append data at the end of the file.

> -r READPATH: read features from READPATH and match

EXAMPLE:

> OpenDIR -w featureout1.txt

> OpenDIR -r featureout3.txt

> OpenDIR -w featureout2.txt -r featureout2.txt


# Simple Demo #

**At the beginning, inputimage.txt should be prepared to indicate the input images as back-end data. We can directly input the relative image path:**

testimg\Capture1.jpg

testimg\Capture1small.jpg

testimg\Capture2.jpg

testimg\Capture2small.jpg

testimg\1.jpg

testimg\2.jpg

testimg\3.jpg

testimg\4.jpg

testimg\5.jpg

testimg\6.jpg

Here is my testimg folder for simple demo, the Capture1small is smaller than Capture1 in size with same content:

![http://farm6.static.flickr.com/5313/5914831326_80faf44d26.jpg](http://farm6.static.flickr.com/5313/5914831326_80faf44d26.jpg)


**Let's go to the command line and extract image features:**

XXX> OpenDIR -w featureout.txt

We can find featureout.txt created with the feature descriptors


**Yeah, we are able to begin to retrieve now~**

XXX> OpenDIR -r featureout.txt

**Try an image in the testimg folder firstly, the result will show the top 5 similar ones:**


...

Please input the retrieval image path:testimg\Capture1.jpg

...



Result:

Most Similar: testimg\Capture1.jpg
> with 100.000000%

Most Similar: testimg\Capture1small.jpg
> with 96.903877%

Most Similar: testimg\Capture2.jpg
> with 90.289092%

Most Similar: testimg\Capture2small.jpg
> with 90.383493%

Most Similar: testimg\2.jpg
> with 80.265278%

Continue retrieval?y(es) or n(o):y


**Great! 100% similar with itself and 96.9% similar with the smaller one.**

**Further more, a harder one:**

This image is captured by my mobile camera and I use CV\_THRESH\_OTSU to binary it.

![http://farm6.static.flickr.com/5320/5914324925_b093ba4727.jpg](http://farm6.static.flickr.com/5320/5914324925_b093ba4727.jpg)



Result:

Most Similar: testimg\3.jpg
> with 74.557813%

Most Similar: testimg\2.jpg
> with 79.548928%

Most Similar: testimg\Capture2.jpg
> with 81.612691%

Most Similar: testimg\Capture2small.jpg
> with 76.995192%

Most Similar: testimg\1.jpg
> with 87.356586%

Continue retrieval?y(es) or n(o):n


87.356586% is highest. Here is the 1.jpg:

![http://farm6.static.flickr.com/5274/5913891843_dd17454e12.jpg](http://farm6.static.flickr.com/5274/5913891843_dd17454e12.jpg)

# 1000+ Performance #

Test environment:

Quad-Core 2376 2.3G, 4G RAM Memory, 32bit-Vista, VS2005 with OpenCV 2.2

Here is the test images, they are 850\*1000 jpg:

![http://farm7.static.flickr.com/6028/5925489016_35e61e5aa1.jpg](http://farm7.static.flickr.com/6028/5925489016_35e61e5aa1.jpg)

Retrieval Result:

![http://farm7.static.flickr.com/6142/5925488906_56379a5cb1.jpg](http://farm7.static.flickr.com/6142/5925488906_56379a5cb1.jpg)

The average is 3.3ms for single image retrieval from 1000 images.