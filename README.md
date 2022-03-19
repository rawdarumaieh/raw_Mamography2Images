# raw_Mamography2Images
Transforming raw mammography to re-presentable image 
#
##### Image Description
- The image size is 4096x3328
- The image is 14 bits therefore the maximum gray level value is 16383
- The output image is a 12-bit image with a maximum gray level value at 4095
#
##### Steps of reaching the final image
* 1- Log transformation
Transformed the gray values from 0-16383 to 0-4095 (12-bit image)
[log equation]
* 2- Inverting the black and white of the image
[maximum value of the pixels – each pixel]
* 3- Examining the histogram of the image then thresholding based on a certain pixel value (below 1000 the pixel’s value = 0, while pixels above 1000 remained the same)
To avoid bright regions before histogram equalization
* 4- Histogram equalization using [skimage.exposure.equalize_hist] Stretches out the intensity range of the image to enhance the contrast. The intensity values we obtained after histogram equalization were ranging from 0-1
* 5- Remapping the values from 0-1 to 0-4095 “12 bits”
