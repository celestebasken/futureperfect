---
author: Celeste
date: "2020-07-28"
description: Blog entry pulled from old R markdown blog
featured: pic03.jpg
featuredalt: Pic 3
featuredpath: date
linktitle: ""
title: Very first intro to R
type: post
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(message=FALSE,warning=FALSE, cache=TRUE)
```


# Introduction to R

I began learning R using the [SWIRL](https://swirlstats.com/students.html) package over the summer. Now I want to try more data work for the Nature Conservancy and the Conservation Data Lab. 

# Testing out my own dataframe

I wanted to make a data set to mess around with, so I made up some data about my friends' family since they have a lot of kids and a lot of dogs.
```{r}
names <- c("Jonny", "Lizzie", "Lauren", "Juliana", "Wooffulls", "Wonka", "Jojo", "Junie")
favNumber <- sample(10, 8)
height <- sample(6, 8, replace = T)
# if the height is less than 5, I want to add 2
height < 5
height[c(1, 4, 5, 7, 8)] <- height[c(1, 4, 5, 7, 8)] + 2
# time for more data!
age <- sample.int(25, size = 8, replace = T)
# this is a list of random words
careers <- c("Nanny", "Pilot", "Gardener", "Barista", "Chef", "Unemployed", "Fast Food",
             "Basketball", "Bachelorette", "Diva", "Lawyer", "Scientist", "Biologist", 
             "HR", "TV Personality", "Army", "Actor", "Politician", "Pirate", "Shark", 
             "Vampire", "Model", "Hermit", "Activist", "Mom", "Dad", "Actor", "Teacher",
             "Warrior", "Journalist", "Bartender", "Police", "The Great American", 
             "Knight", "Millionaire", "Robber", "Celebrity", "Mathematician", "Construction",
             "Bachelor", "Momma's boy", "Royal", "Mermaid", "Soccer player", 
             "Rock climber", "Doctor", "Diver", "Logging", "Hollywood", "Nothing", 
             "Secretary", "CEO", "Cat Lady", "Dentist", "Hair cutter", "Filmmaker",
             "Newscaster", "Truck driver", "Architect", "Hunter", "Farmer", "Amish", 
             "Rabbi", "Rock n Roll", "Personal trainer", "Author", "Kid", "Bus driver",
             "Publisher", "Editor", "President", "Philanthropist", "Advertiser")
chosenCareers <- sample(careers, 8)
coast <- sample(c("East Coast", "West Coast", "not America", "Middle"), 8, replace = T)
favGreenwoodBasken <- sample (c("Celeste", "Freddie", "Gram", "Gramps", "Maureen",
                                "Paul"), 8, replace = T)
favGreenwoodBasken
catdog <- sample(c("cats", "dogs"), 8, replace = T)
data.frame(names, favNumber, height, age, chosenCareers, coast,favGreenwoodBasken,
           catdog)
````

