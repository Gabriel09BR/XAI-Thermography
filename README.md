🩺 Detection and Classification of Breast Lesions Using Explainable Machine Learning

  Supplementary repository for the article:
  “Detection and Classification of Breast Lesions in Biomedical Images Using Explainable Machine Learning Techniques”
  Authors: Gabriel Luiz Limeira Barreto, Prof. Dr. Sidney Marlon Lopes de Lima (advisor)
  📄[Access the published article here](https://periodicos.newsciencepubl.com/arace/article/view/8436)
  
  
# Overview

This repository provides the segmentation masks and feature descriptions that achieved the best experimental results in the study presented in the article above.
The main goal is to ensure reproducibility, interpretability, and transparency in biomedical image analysis by sharing the explainable features used for lesion detection and classification.

These data were extracted from mammographic regions of interest (ROIs) and include shape, texture, and color descriptors, which are fundamental for both classification and model explainability.













# Description of Shape and Texture Features

| **Attribute** | **Description** |
|---|---|
| **Color: MSE between the mask and the active region** | A measure of error between the colors of an RGB pattern of the decomposed and self-remodeled mask during execution, in relation to the active region of the image. This suggests a metric that calculates the mean squared error between the colors of these patterns in different regions of the image. |
| **The amount of mask decomposition** | A proportion of the number of pixels remaining in the decomposed mask relative to its original size. Providing a measure of the preservation or loss of information during the mask decomposition process. |
| **Shape descriptor: Area** | Actual number of pixels in the region, represented as a scalar. |
| **Shape descriptor: Centroid** | Center of mass of the region, returned as a 1-by-Q vector, where Q is the dimensionality of the image. The first element of the centroid is the horizontal coordinate of the center of mass. The second element is the vertical coordinate. All other elements of the centroid are in order of dimension. |
| **Shape descriptor: Bounding box(1)** | Used to compute the bounding box of a set of points or objects in an image. This bounding box is a rectangle that completely encloses the points or objects. The function returns the coordinates of the bounding box, usually in the form \[xmin, ymin, width, height\], where Bounding box(1) represents only **xmin**. |
| **Shape descriptor: Bounding box(2)** | Similar to the previous one, where Bounding box(2) represents only **ymin**. |
| **Shape descriptor: Bounding box(3)** | Similar to the previous one, where Bounding box(3) represents only **width**. |
| **Shape descriptor: Bounding box(4)** | Similar to the previous one, where Bounding box(4) represents only **height**. |
| **Shape descriptor: Major axis length** | Length (in pixels) of the major axis of the ellipse that has the same normalized second central moments as the region, returned as a scalar. |
| **Shape descriptor: Minor axis length** | Length (in pixels) of the minor axis of the ellipse that has the same normalized second central moments as the region, returned as a scalar. |
| **Shape descriptor: Eccentricity** | Eccentricity of the ellipse that has the same second moments as the region, returned as a scalar. The eccentricity is the ratio of the distance between the foci of the ellipse and its major axis length. The value is between 0 and 1. An ellipse whose eccentricity is 0 is actually a circle, while an ellipse whose eccentricity is 1 is a line segment. |
| **Shape descriptor: Orientation** | Angle between the x-axis and the major axis of the ellipse that has the same second moments as the region, returned as a scalar. The value is in degrees, ranging from -90 degrees to 90 degrees. |
| **Shape descriptor: Convex Area** | The "Convex Area" refers to the number of pixels in the "Convex Image", that is, the image that specifies the convex hull of the region of interest, where all pixels inside the hull are filled (considered as "on"). This area is returned as a scalar value. |
| **Shape descriptor: Filled Area** | "Filled Area" is the count of the number of on pixels in the filled image (Filled Area), which specifies a region with all pixels inside the contour filled (on), returned as a scalar value. |
| **Shape descriptor: Euler Number** | Calculates the number of connected regions minus the number of holes in the region of interest in a binary image. This provides information about the topology of the region, helping to distinguish between different shapes and structures present in the image. The higher the Euler number, the more complex the structure of the region. |
| **Shape descriptor: Extrema(1)** | Coordinates of the top-left corner of the bounding box that encloses the region of interest in an image. This allows determining exactly where the region starts and ends in the image, facilitating a variety of operations, such as cropping, position measurement, and calculation of region size. |
| **Shape descriptor: Extrema(2)** | Coordinates of the top-right corner of the bounding box that encloses the region of interest in an image. |
| **Shape descriptor: Extrema(3)** | Coordinates of the upper right part of the bounding box that encloses the region of interest in an image. |
| **Shape descriptor: Extrema(4)** | Coordinates of the bottom-right corner of the bounding box that encloses the region of interest in an image. |
| **Shape descriptor: Extrema(5)** | Coordinates of the lower-right part of the bounding box that encloses the region of interest in an image. |
| **Shape descriptor: Extrema(6)** | Coordinates of the bottom-left corner of the bounding box that encloses the region of interest in an image. |
| **Shape descriptor: Extrema(7)** | Coordinates of the lower-left part of the bounding box that encloses the region of interest in an image. |
| **Shape descriptor: Extrema(8)** | Coordinates of the top-left corner of the bounding box that encloses the region of interest in an image. |
| **Shape descriptor: Equivalent Diameter** | Diameter of a circle with the same area as the region, returned as a scalar. Calculated as sqrt(4 \* Area / π). |
| **Shape descriptor: Solidity** | Proportion of the pixels in the convex hull that are also in the region, returned as a scalar. Solidity is calculated as Area / Convex Area. |
| **Shape descriptor: Extent** | Ratio of pixels in the region to pixels in the total bounding box, returned as a scalar. Calculated as the Area divided by the area of the bounding box. |
| **Shape descriptor: Pixel idx list** | Linear indices of the pixels in the region, returned as a vector of p elements. |
| **Shape descriptor: Pixel list** | Locations of the pixels in the region, returned as a p x Q matrix. Each row of the matrix has the form \[x y z ...\] and specifies the coordinates of a pixel in the region. |
| **Shape descriptor: Perimeter** | Distance around the boundary of the region, returned as a scalar. The perimeter is calculated by computing the distance between each pair of adjacent pixels around the boundary of the region. If the image contains noncontiguous regions, the result will be unexpected. |
| **Shape descriptor: PerimeterOld** | Distance around the boundary of the region, returned as a scalar. The perimeter is calculated by counting only the border pixels around the object, without considering the diagonals. |
| **Texture descriptor: Entropy** | Entropy is calculated based on the distribution of pixel intensities in the image. An image with high entropy indicates a more uniform distribution of intensities or a more complex image, while an image with low entropy indicates a more concentrated distribution of intensities or a simpler image. |
| **Texture descriptor: Contrast** | A measure of the variation of gray levels in the image. It quantifies the difference in intensity between adjacent pixels in a certain direction and distance in the image. The higher the contrast, the greater the difference between the intensity values of neighboring pixels, indicating abrupt changes in the texture of the image. |
| **Texture descriptor: Correlation** | A measure of the linearity of the relationship between gray levels in the image. It quantifies the degree of correlation between the intensity values of pixels in a certain direction and distance in the image. The correlation ranges from -1 to 1, where values close to 1 indicate a strong positive correlation (pixels tend to have similar values) and values close to -1 indicate a strong negative correlation (pixels tend to have opposite values). A correlation value close to zero indicates a lack of linear correlation. |
| **Texture descriptor: Energy** | Energy is a measure of how concentrated or dispersed the gray level distribution is in the image. The higher the energy, the more uniform the texture of the image. This measure is useful for distinguishing between uniform textures and textures with abrupt intensity changes. |
| **Texture descriptor: Homogeneity** | A measure of the uniformity or regularity of the gray levels in the image. It quantifies how close the intensity values of the pixels are to each other. The higher the homogeneity, the lower the variation in gray levels between neighboring pixels, indicating a more uniform and regular texture in the image. |
| **Global color information: Manual crop** | Amount of pixels eliminated through manual cropping, described in subsection 4.1.3. |
| **Global color information: Dark purple** | Histogram of the dark purple color range. |
| **Global color information: Light purple** | Histogram of the light purple color range. |
| **Global color information: Dark blue** | Histogram of the dark blue color range. |
| **Global color information: Light blue** | Histogram of the light blue color range. |
| **Global color information: Green** | Histogram of the green color range. |
| **Global color information: Yellow** | Histogram of the yellow color range. |
| **Global color information: Red** | Histogram of the red color range. |
| **Global color information: White** | Histogram of the white color range. |
