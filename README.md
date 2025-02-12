# Persistent Homology Tool for Branch Structure Analysis

## Motivation
When analyzing branch structures, we often separate internal and external structures.

However, their separation is sometimes ambiguous, and an objective tool to define the internal and external structures is beneficial.

## What is this?
Here, we provide a tool to define internal and external structures in branches using persistent homology.

This tool allows us to tune the internal and external structures in an objective, quantitative, and reproducible way.

## Method
Given a point cloud $X$ (white pixels in the original branch image), we add new points $U$ on the boundary of the convex hull of $X$.

(In this code, we use convex hull, but you can make modification here.)

Now, we calculate persistent homology (alpha complex filtration) for $X$ and $X\cup U$.

Then, we get persistence diagrams $PD_1(X)$ and $PD_1(X\cup U)$.

We define the internal structure as $PD_1(X)\cap PD_1(X\cup U)$ and the external structure as $PD_1(X\cup U)\backslash PD_1(X)$.

We can visualize our internal and external structures with a simple inverse analysis. 

The blue circle plots correspond to the internal structure and the red diamond plots correspond to the external structure.

## Parameter tuning
Our parameter for changing the internal and external structures is the $U$ above.

In this code, we change $U$ by the $\texttt{dist}$ variable. $\texttt{dist}$ represents the interval of the points we plot on the boundary of the convex hull.

(You can make it more flexible by allowing manual inputs, etc.)

Tips for parameter tuning can be found in the related paper below.

## Related Paper (This information is old. We will link to the latest version soon.)
This code is based on the following article:

https://doi.org/10.48550/arXiv.2402.07436

In this paper, we verify our tool from different perspectives.

## Persistent homology calculation
This code uses HomCloud for the persistent homology calculation.

The installation guide for HomCloud can be found here.

https://homcloud.dev/index.en.html

