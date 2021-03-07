---
title: Building a new website!
author: Celeste Basken
date: '2021-03-07'
slug: []
categories: []
tags: []
description: ''
featured: ''
featuredalt: ''
featuredpath: ''
linktitle: ''
type: post
---

# New website!
I'm making a new website! Don't worry, it's not a new R blog- I just made this one and I'm still quite happy with it. I'm making a portfolio because, as a high school junior, I'm starting the college application process and I want a place to showcase my work that is prettier than LinkedIn. 

After making probably 5 repositories from different Hugo Blogdown themes (I basically have all of their themes memorized at this point), I finally commited to a relatively simple one called Airspace (thanks to [Theme Fisher](https://github.com/themefisher/airspace-hugo) on Github!). 

After building the website in R studio, with a repository in Github and hosted on Netlify, I decided to splurge and buy a domain from Google Domains. I bought [celestebasken.com](celestebasken.com) for $12/ year, which I think is a pretty fair price given my unique-ish name.  

I want to try and document some of the notable challenges I encountered in the first 48 hours of my young website (it's still quite young!), but unfortunately I was so enthralled in customizing everything that I definitely did not blog along. I'm trying to recreate some of it here.

UNRELATED BUT IMPORTANT: I don't know where to put this, but it's important so I'll throw it in here: before building the site, I added the following line at the bottom of the default configurations in config.toml. 

````
ignoreFiles = ["\\.Rmd$", "\\.Rmarkdown$", "_cache$", "\\.knit\\.md$", "\\.utf8\\.md$"]
```

# First challenge: how to build the site??
I think this varies slightly based on the Hugo site, but I was caught very unawares because I couldn't figure out how to build my dang site! (Elementary, I know.) 

I'm spoiled because this blog, and the accompanying theme Future Imperfect, has an integrated 'build' button right in R-studio. For whatever reason, the Airspace theme did not have such a button, and I found myself stuck before I had truly begun. I realized that all the 'build' button does is run the line blogdown::build_site() so that was quite a relief. Issue #1: Solved!

# How to change the page names?
I also encountered trouble changing the names of the main pages on my site (such as "films," "extracurriculars," etc). I figured out that in config.toml the name parameter is what appears on the site. Good to know.

The 'parent' field refers to the fact that this particular page is nested under the 'parent' Extracurriculars. That means that in the heading on my site, if you click the drop down on parent, then you see Model United Nations. 

```
[[Languages.en.menu.main]]
  parent = "Extracurriculars"
  name = "Model United Nations"
  URL = "mun"
  ```
The code to set up extracurriculars is here: 

```
weight = 6
name = "Extracurriculars"
hasChildren = true
```
The 'hasChildren' field enables it to be a parent. Cute.

# How to disable languages
A lot of Hugo themes are bilingual, which is great if you are, but since I only want to deal with English right now, I added the following to config.toml in the bottom of the first set of default configurations (right near ignoreFiles!)
```
disableLanguages = ["fr"] #Note that the only other language for Airspace was French.
```
