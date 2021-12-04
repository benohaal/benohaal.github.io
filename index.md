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
<center><img src="assets/images/WRP.png" width="400" height="200" /><br><span>Figure 1: A watchman route example</span></center>

## Prelimenaries

In this section, we will give some basic terminology and definitions, which will be useful later on.

The polygons we consider in this report are n-sided (n edges) simple (no holes and don't self-intersect) polygons.
They have n edges and n vertices, where n >= 6. This is because simple polygons with n <= 5 sides only need one static guard to solve the problem. Moreover, the polygons shouldn't be starshaped, as there exists, per definition, one point in them from which every other point is visible.

Inside of the polygons, we'll find two kinds of vertices. The ones with an inner angle of less than 180° and those with an inner angle of more than 180°. They are called convex and reflex vertices respectively. Note that a polygon with only convex vertices is called a convex polygon.

A convex hull is defined as the smallest convex set S containing a given shape (e.g. a polygon), where the convex set is a set of points such that for any two points x, y &#8712; S, the segment [x, y] is in the convex set. For convex polygons, the convex hull is equal to the polygon itself. Note that every convex polygon can, again, be guarded by only one static guard.

Tangents, in polygons, are lines or line segments that, locally, only intersect with one point of the polygon. They touch the polygons boundary but dont cross it. They can be inside or outside of the polygon.

Polygon triangulation is the decomposition of polygons into a set of triangles. There can be many triangulatations of a same polygon with more than 3 vertices. Many different triangulation algorithms exist.

## Problem definition

As mentionned before, we will consider the watchman route problem in the case of simple polygons. We will review this problem in the fixed version, for which the route must go through a start point (a "door") located on the boundary of the polygon. This is opposed to the floating variant, for which no fixed point is specified.

Finding the shortest route for this problem is not trivial, as there can be an infinite number of routes and paths inside a polygon.
An optimal solution was found by xxx in [?] and has a time complexity of O(n^3 log n). Hence it is of interest to find a linear time approximation algorithm. In [?], xxx presents a 2-approximation linear time algorithm to solve the watchman route problem, meaning that the solution is at most 2 times as long as the optimal solution. To give an idea of the magnitude of this result, a previous article [?] had a solution that was at most 99,.. times longer than the shortest watchman route.


## First approach

We will now present a solution, without any promises of optimality, using the tools we know. From there, we will work towards a better solution that yields better results. 

A first solution idea, using what we already know, bases on the triangulation of polygons. It is easy to see that if we visit every triangle of a triangulated polygon, we will have seen every point of the polygon. In fact, as a triangle is a convex shape, for any two points inside of it there exists a segment between those points that lies entirely inside the triangle. Adding to this, we can define the dual tree of a triangulated polygon as follow. For every triangle we add a node inside of it. Then, we bind two nodes together if their associated triangles share an edge.

<center><img src="assets/images/dual_tree.png"/><br><span>Figure 2: Left, a polygon. Right, the dual tree of the polygon</span></center>

A watchman route can thus be defined as a route that visits the triangles along a path defined by the branches of the dual tree. Notice however that such a closed route visits the triangles multiple times, except for the ears of the polygon. This is far from optimal.

If we pay attention to Figure 2, we can see that some triangles are entirely visible from points of the polygon that are not part of the triangle. Thus, we need to find a way to define bigger parts of the polygon that would need to be visited only once in a shortest watchman route. This can be done with something called essential cuts. The second part of this section will be dedicated to defining these.



Using chords (line segments) that go through two vertices, we can split the polygon into two pieces. We refer to these partitions as cuts.

What we essentially want our guard to do, is to peak behind every corner of the polygon. Using cuts, we can split the polygon into one part that is totally visible from any point of the cut and the other part that 
-reflex vertices
-extend edge
-obtain a cut

<center><img src="assets/images/polygon_ears.png"/><br><span>Figure 3: From left to right we have a polygon, a triangulated polygon and a polygon with two essential cuts</span></center>

Actually you can do better. Extension of a reflex edge. Cuts. Dominance. Essential cuts. 

**Note: This is only a placeholder**

<iframe src="https://codesandbox.io/embed/triangulation-of-polygons-1dvyl?fontsize=14&hidenavigation=1&theme=dark&view=preview"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title="Triangulation of polygons"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>
   [Access the code directly](https://codesandbox.io/embed/triangulation-of-polygons-1dvyl?fontsize=14&hidenavigation=1&theme=dark&view=preview)

## Shortest route

Shortest path as a solution to the WRP goes through every essential cut => Idea behind is that we want to peak behind corners.
Shortest path visits the essential cuts in the order of their defining vertex.
One WRP solution : middle of every essential cut and through the "door".
Link to TSP with neighberhoods & Zookeeper problem.
Discuss an approximation algorithm presented in [?] by xxx.

## Approximation

Rubberband algorithm + idea
ESP (polygon triangulation, funels)
tangent
convex hull

## Conclusion

The Watchman route problem is an interesting problem in computational geometry that makes use of a lot of basic notions (which we have seen in class).
The problem is still relevant, as it can have a lot of applications in the age of robotics and autonomous vehicles/robots.
Finding (approximated) solutions for the problem is however not an easy task and most articles on the subject present "simple" solutions, that actually aren't.
   
## References
https://www.researchgate.net/publication/220991554_Watchman_Route_in_a_Simple_Polygon_with_a_Rubberband_Algorithm
