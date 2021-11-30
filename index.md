---
title: Watchman Route Problem
---

### Abstract

The watchman route problem is an optimization problem related to the famous art gallery problem. The problem is the following.
Given a simple polygon, we want to find the shortest (closed) route such that any point inside the polygon is visible from at least one point of the route.
This website contains all the definitions needed to apprehend the problem, aswell as simple-ish approximation algorithm to find a good solution to the problem.

## Introduction

To better understand the presented problem, let's review the art gallery problem first. The art gallery problem is a visibility problem in computational geometry, that consists in finding the minimum number of guards needed to cover every spot of a polygon (the art gallery). The guards are static and sometimes referred to as cameras.
By replacing the static guards with guards that can move along a line segment, one obtains the art gallery problem with mobile guards. In this variant, the objective is still the same as with the original problem. It however requires a new definition of visibility. When we talked about visibility with static guards, we implicitly meant strong visibility, such that every point of the polygon is visible at all times by one of the guards. This is not required anymore and leads to the definition of weak visibility, for which, every point of the polygon should be visible by at least one point on the line segments of the guards.
If we now allow the guards to move along a closed chain of segments, known as a closed path, and by reducing the number of guards to 1, we obtain the so called Watchman route problem. 
<center><img src="github_img_test.png" width="400" height="200" /></center>

## Prelimenaries

## Problem definition

## First approach

**Note: This is only a placeholder**

<iframe src="https://codesandbox.io/embed/triangulation-of-polygons-1dvyl?fontsize=14&hidenavigation=1&theme=dark&view=preview"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title="Triangulation of polygons"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>
   [Access the code directly](https://codesandbox.io/embed/triangulation-of-polygons-1dvyl?fontsize=14&hidenavigation=1&theme=dark&view=preview)

## Shortest route

## Conclusion


   
## References
https://www.researchgate.net/publication/220991554_Watchman_Route_in_a_Simple_Polygon_with_a_Rubberband_Algorithm
