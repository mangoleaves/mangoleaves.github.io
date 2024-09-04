---
title: "Exact and Efficient Intersection Resolution for Mesh Arrangements"
layout: project
permalink: /projects/mesh-arrangements/
author_profile: false
date: 2024-01-01
venue: 'ACM Transactions on Graphics (Proc. SIGGRAPH)'
issue: "43(6)"
authors: 
  - name: "Jia-Peng Guo"
    url: "https://mangoleaves.github.io"
  - name: "Xiao-Ming Fu"
    url: "https://ustc-gcl-f.github.io/"
affiliations:
  - name: "University of Science and Technology of China"
    url: "http://www.ustc.edu.cn/"
teaser:
  image: "/images/2024-mesh-arrangements/Problem.png"
  long: false
  caption: "Our algorithm exactly resolves intersections and self-intersections within general triangle meshes (left) without any additional assumption and produces triangulated results that completely preserve input geometry (bottom right). It enables mesh arrangements to further partition space into closed and consistently oriented cells (top right)."
sidebar:
  title: "Navigation"
  nav:
    - title: "Abstract"
      url: "/projects/mesh-arrangements/#abstract"
    # - title: "Motivation"
    #   url: "/projects/mesh-arrangements/#motivation"
    # - title: "Methodology"
    #   url: "/projects/mesh-arrangements/#methodology"
    - title: "Results"
      url: "/projects/mesh-arrangements/#results"
    - title: "Resources"
      url: "/projects/mesh-arrangements/#resources"
    - title: "Acknowledgement"
      url: "/projects/mesh-arrangements/#acknowledgement"
    - title: "Cite us"
      url: "/projects/mesh-arrangements/#cite-us"
---

## Abstract

<p style="text-align: justify;">
We propose a novel method to exactly and efficiently resolve intersections and self-intersections in triangle meshes.
Our method contains two key components.
First, we present a new concept of geometric predicates, called indirect offset predicates, to represent all intersection points through a new formulation and establish all necessary geometric predicates.
Consequently, we reduce numerical errors in floating-point evaluations and improve the success rate of early stages of arithmetic filtering.
Second, we develop localization and dimension reduction techniques for sorting, deduplicating, and locating the intersection points, thereby boosting efficiency and parallelism while maintaining accuracy.
Rigorous testing confirms the robustness of our algorithm and consistency with previous methods.
Comprehensive testing across diverse datasets further highlights the speed improvement achieved by our method, which is one order of magnitude faster than the state-of-the-art methods.
</p>

<!--
## Motivation

<p style="text-align: justify;">
Intersection resolution is the crucial initial stage of mesh arrangements.
The motivation stems from two key observation:
</p>

<ol style="text-align: justify;">
<li>
the geometric primitives involved in constructing intersection points exhibit good locality, leading to predicate expressions with reduced numerical errors and higher success rates for floating-point filters;
</li>
<li>
the problem's inherent locality and low-dimensional nature allows for localized and dimension-reduced processing, thereby enhancing the algorithm's efficiency and parallelism.
</li>
</ol>

## Methodology

<p style="text-align: justify">
To effectively leverages the locality of geometric primitives involved in constructing intersection points, we propose <i>offset indirect predicates</i> by extending the concept of <i>indirect predicates</i>.
The expression of implicit points is reformulated to the sum of base and offset parts, so that the predicates involving such implicit points consist exclusively of terms involving coordinate differences.
The locality in intersection construction often results in coordinate differences being several orders of magnitude smaller than the coordinate values themselves.
This leads to smaller numerical errors in offset indirect predicates during (semi-)static floating-point filtering, thereby increasing the success rate of the corresponding filters.
</p>

<p style="text-align: justify">
We extend our predicates by building on the existing foundation and further optimizing the algorithm.
To efficiently deduplicate intersection points, we localize this process by sorting the intersection points along their respective edges or segments, rather than using a global map. This localization significantly reduces the sorting scale by several orders of magnitude and enhances the parallelism.
Additionally, to reduces the number of calls to the computationally expensive predicates, we simplify the constrained triangulation by reducing it to a 2D problem through the projection of triangles onto an orthogonal plane, and further simplify the intersection location process and introduces a new property.
</p>
-->

## Results

We test our algorithm on the Thingi10k dataset and one stress-testing dataset (constructed by rotating one models several times and combining all of them) to validate the robustness and efficiency of our algorithm. Compared with the state-of-the-art methods, the efficiency is improved by an order of magnitude. See details in our paper :).

<figure style="width: 90%; text-align: center;">
  <img src="/images/2024-mesh-arrangements/Gallery.png" alt="Gallery">
  <figcaption style="text-align: center;">
    Industrial CAD models from GrabCAD, containing numerous self-intersections. The intersections are resolved by our algorithm. The number of vertices (#V), number of faces (#F), number of intersecting triangle pairs (#Int), and the runtime of our algorithm (Time) are also shown in the figure.
  </figcaption>
</figure>

## Resources

* [Paper](/files/2024-mesh-arrangements/MeshArrangements.pdf)
* [Supplementary](/files/2024-mesh-arrangements/MeshArrangements-supp.pdf)
* [Code](https://github.com/mangoleaves/OpenMeshCraft)
* [Data](/files/2024-mesh-arrangements/ModelList.zip)

## Acknowledgement

We would like to thank the anonymous reviewers for their constructive suggestions and comments.
This work is partially supported by the National Natural Science Foundation of China (62272429).

## Cite us

```
@article {guo2024arrangements,
    title = {Exact and Efficient Intersection Resolution for Mesh Arrangements},
    author = {Guo, Jia-Peng and Fu, Xiao-Ming}
    journal = {ACM Transactions on Graphics},
    volume={43},
    number={6},
    pages={1--14},
    year = {2024}
}
```
