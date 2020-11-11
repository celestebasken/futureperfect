---
author: Celeste
categories:
- Hugo
date: "2020-11-06"
description: Blog entry pulled from old R markdown blog
featured: pic03.jpg
featuredalt: Pic 3
featuredpath: date
linktitle: ""
tags:
- tutorial
title: Fixing graphs and things
type: post
---

It's been a little while since I blogged and I created some graphs! Today I'm just cleaning them up and fixing issues, like bunched-up letters or skinny lines. 


I learned more about [R bar graphs](http://r-graph-gallery.com/), which was nice because I've been using them without really understanding what they do. I still don't fully understand each piece, but I figured out enough to insert the line 
````{r}
width="1"
````
into my ggplot graph. I tried changing the theme, but that didn't work and said it couldn't find the function. I tried loading ggplot2 and the other libraries again but that didn't fix it, so I probably just don't have the theme. I'm overall really excited to try out all the cool graphs on R Graph Gallery. 

I'm also in the process of creating my new blog. Right now I'm writing on a forked markdown from the Crump Lab on GitHub but I want to make a more personalized one from scratch so I understand what's going on. I created a Blogdown graph with a pretty theme but I may end up tossing that one as well because it's so advanced and I have no idea what's going on.