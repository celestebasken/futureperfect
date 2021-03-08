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
````

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
  ````
The code to set up extracurriculars is here: 

```
weight = 6
name = "Extracurriculars"
hasChildren = true
````
The 'hasChildren' field enables it to be a parent. Cute.

# How to disable languages
A lot of Hugo themes are bilingual, which is great if you are, but since I only want to deal with English right now, I added the following to config.toml in the bottom of the first set of default configurations (right near ignoreFiles!)
```
disableLanguages = ["fr"] # Note that French was the only other language
````

# Connecting my Google Domain to my Netlify using DNS
This step was challenging. Luckily, there were people on the internet to help. In Google Domains, I selected the DNS tab on the sidebar and clicked 'Use custom name servers' on the first block called Name servers. Then I headed over to Netlify and set up a Netlify DNS. It basically gave me four 18-character strings starting in dns and ending in net, which I was able to copy and paste into Google domains. I hit save and it... worked!? (Immediately in fact!)

Since I relied heavily on aforementioned 'people on the internet,' I'm going to link a couple good ones here, because I don't know if my explanation just now made any sense. Here's what I used:
* [This Medium article](https://medium.com/@jacobsowles/how-to-deploy-a-google-domains-site-to-netlify-c62793d8c95e) is amazing, with pictures and everything! Thanks Jacob Sowles!
* [Dev.to's article](https://dev.to/lost_semicolon/netlify-and-google-domains-hm3) which uses fancier- but more accurate- terms and maybe will help if you're stuck on the Medium article.
* [Here is the Storybench article](https://www.storybench.org/how-to-build-a-website-with-blogdown-in-r/) that is my overall guide to the whole Blogdown Hugo process. Super helpful. Probably should have mentioned it earlier.

# The favicon!
What is a favicon? It's that teeeny tiny little logo (I mean tiny- it's only 32x32 pixels) in the tab on your browser. In my opinion it makes SUCH a difference for websites because without it, they always look a little unfinished and unprofessional.

The favicon was an obsession of mine. I could NOT get it to work. And then I found...

[TOM FRANKLIN.CO!!!!](https://www.tomfranklin.co.uk/portfolio/favicon/)

The ironic part about the whole thing is that Tom Franklin's own site doesn't have a favicon, but maybe it's an aesthetic choice. IDK. Anyways.

I could restate what he says but honestly once I found that website, it was smooth sailing. Follow what he says. The only thing I would add- once I got to the HTML file, I was confused because it APRPEARED to already include the line he said. When I looked closer, I realized my line said 
```
<link rel="icon" href="{{ "img/favicon.png" | absURL }}" type="image/x-icon"> # Note the favicon file extension
````
and not 
````
<link rel="icon" href="{{ "img/favicon.ico" | absURL }}" type="image/x-icon">
````

I also put the favicon.ico file in way more places than he does. I had a copy of favicon.ico in your_blog_name/static/images, one in your_blog_name/public/images, and one in your_blog_name/themes/your_theme_name/example/static/images. Maybe it's overkill. But it works!! 
