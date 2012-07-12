---
layout: post
title: Reverse Geocoding Of Geographic Coordinates to Map Regions
---

Choropleth maps are a great way to visualize geo data.

> [Reverse geocoding](http://en.wikipedia.org/wiki/Reverse_geocoding) is the process of back (reverse) coding of a point location (latitude, longitude) to a readable address or place name.

In this case, we don't need to know the exact address but just the name/id of a region in our map. Here's the example.

For the sake of this tutorial we want to assign party donations to election districts. For each donation we have the geographic coordinate of the donor, but we don't know to which election district the location belongs to.

What we need now is a shapefile that contains the election districts.



## 