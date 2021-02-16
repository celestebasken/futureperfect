---
author: Celeste
date: "2020-12-31"
description: A self-cheatsheet for when I get stuck
featured: pic03.jpg
featuredalt: Pic 3
featuredpath: date
linktitle: ""
title: Notes to Self
type: post
---

Here are a couple things to check for if/ when I'm having R trouble. This is certainly not an exhaustive list and it only includes issues I've seen before, but I hope this will be a productive way to keep track of things I run into time and time again.

When referencing files doesn't work
* Set the working directory to the main folder and try again.
````{r}
setwd()
```` 
* Check spelling! This one is so easy to get caught on. Copying and pasting should do the trick.
* Check the file extension name (such as geojson vs json).
* Check for spaces! If a file name has spaces in in, preferably a) remove the spaces and if not b) use `` around the file name, such as
````{r}
`data set`
````

As I said, this is a very preliminary list, but I hope to add to it as I progress (and encounter issues) in R.