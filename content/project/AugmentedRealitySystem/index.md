---
title: Augmented Reality system using Planar Homographies.
summary: Planar homography is a warp operation that maps pixel coordinates from one camera frame to another with the fundamental assumption that the points are lying on a plane in the real world. This concept allows us to create cool applications such as an augmented reality system or a panorama stitcher.
tags:
- Computer Vision
date: "2016-04-27T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Photo from EURASIP Journal on Advances in Signal Processing.
  focal_point: Smart

links:
# - icon: twitter
#  icon_pack: fab
#  name: Follow
#  url: https://twitter.com/georgecushen
url_code: "https://github.com/SaiPrahladh/Course-Projects/tree/master/Computer_Vision/AugmentedRealitySystem"
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---
**MOTIVATION:**

Planar homography is a warp operation that maps pixel coordinates from one camera frame to another with the fundamental assumption that the points are lying on a plane in the real world. Under this assumption the mapping can be expressed as 
x1 ≡ Hx2, 
where x1 and x2 are homogeneous coordinates and H is the homography matrix.

**HOW DOES THE MAPPING WORK?**

Before  finding the homography matrix between an image pair, we need to find corresponding point pairs between 2 images. We shall use an interest point detector to find particular salient points in the images around which we shall extract feature descriptors. These descriptors try to summarize the content of the image around the feature points in as succinct yet descriptive manner possible.The matching then can be performed by finding the descriptors in either images with the smallest corresponding distance measure ( eg: Euclidean distance). This can be achieved by using FAST detector along with the BRIEF descriptor.
We can use these matched points to calculate the Planar Homography matrix that will represent the mapping. The numerical stability of the solution can be improved by normalizing the Homography matrix such that
1. Mean of the matrix is now the origin
2. The maximum absolute value of the matrix is 1
We can then implement RANSAC to compute a homography. The best homography matrix would be the one with the most inliers found during RANSAC. 

See the code and this document https://docs.google.com/document/d/1DErhbBJI4_fr6daAV_Dbo2ECviJ8Sqvarmr163pYWp4/edit?pli=1 to check out the results of the project!

