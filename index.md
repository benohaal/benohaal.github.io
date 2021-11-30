---
title: Watchman Route Problem
---

### Abstract

The watchman route problem is an optimization problem related to the famous art gallery problem. The problem is the following.
Given a simple polygon, we want to find the shortest (closed) route such that any point inside the polygon is visible from at least one point of the route.
This report contains all the definitions needed to apprehend the problem, aswell as simple-ish approximation algorithm to find a good solution to the problem.

## Introduction

To better understand the presented problem, let's take a look at the art gallery problem first. The art gallery problem is a visibility problem in computational geometry, that consists in finding the minimum number of guards needed to cover every spot of a polygon (the art gallery). The guards are static and sometimes referred to as cameras.

By replacing the static guards with guards that can move along a line segment, one obtains the art gallery problem with mobile guards. In this variant, the objective is still the same as with the original problem. It however requires a new definition of visibility. When we talked about visibility with static guards, we implicitly meant strong visibility, such that every point of the polygon is visible at all times by one of the guards. This is not required anymore and leads to the definition of weak visibility, for which, every point of the polygon should be visible by at least one point on the line segments of the guards.

If we now allow the guards to move along a closed chain of segments, known as a closed path, and by reducing the number of guards to 1, we obtain the so called Watchman route problem. 
<center><img src="github_img_test.png" width="400" height="200" /></center>

## Prelimenaries

In this section, we will give some basic terminology and definitions, which will be useful later on.

The polygons we consider in this report are n-sided (n edges) simple (no holes and don't self-intersect) polygons.
They have n edges and n vertices, where n >= 6. This is because simple polygons with n <= 5 sides only need one static guard to solve the problem. Moreover, the polygons shouldn't be starshaped, as there exists, per definition, one point in them from which every other point is visible.

Inside of the polygons, we'll find two kinds of vertices. The ones with an inner angle of less than 180° and those with an inner angle of more than 180°. They are called convex and reflex vertices respectively. Note that a polygon with only convex vertices is called a convex polygon.

A convex hull is defined as the smallest convex set S containing a given shape (e.g. a polygon), where the convex set is a set of points such that for any two points x, y &#8712; S, the segment [x, y] is in the convex set. For convex polygons, the convex hull is equal to the polygon itself. Note that every convex polygon can, again, be guarded by only one static guard.

Tangents, in polygons, are lines or line segments that, locally, only intersect with one point of the polygon. They touch the polygons boundary but dont cross it. They can be inside or outside of the polygon.

Polygon triangulation is the decomposition of polygons into a set of triangles. There can be many triangulatations of a same polygon with more than 3 vertices. Many different triangulation algorithms exist.

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

## Approximation

## Conclusion


   
## References
https://www.researchgate.net/publication/220991554_Watchman_Route_in_a_Simple_Polygon_with_a_Rubberband_Algorithm
