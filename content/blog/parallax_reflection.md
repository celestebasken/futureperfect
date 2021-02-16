---
author: Celeste
categories:
- Parallax
date: "2021-02-14"
description: Notes from my experience with Parallax
featured: pic03.jpg
featuredalt: Pic 3
featuredpath: date
linktitle: ""
tags:
- tutorial
title: Parallax Reflection
type: post
---

# An overview of my parallax experience

I've spent the past month or so working with LANDFIRE's national data of area burned in the continental US prior to European colonization. It's a fascinating dataset and I've learned a lot about different chart types, how to make maps, and other valuable skills. My goal from the beginning was to format the charts and text into a parallax, which is a neat style of scrolling document that I've discussed on this blog before.

Neither Randy nor I had very much experience with the parallaxr function- which will be an important note later- and at the beginning I was mainly focused on creating graphs and charts separately. I made bar graphs, presentable data tables, a hexbin map, a ggplot map, and an interactive leaflet map, which was the most hands-on experience I've ever had. 

# The initial issue

Once it came time to format the maps into the parallax, I kept running into issues. I recreated my parallax repository four times! (So much for third time's the charm!) My first issue came from knitting the markdown files that each composed one page of the parallax. The knitted HTML file went into the same folder as the markdowns. A keener eye than mine at the beginning would have been able to see the issue with that immediately from the code below:

````
## SHOULD create a character vector of desired MD files
all_md_str <- list.files(path = "examples/Markdown", full.names = TRUE)

## Loop through each MD file, parse, and return a single tibble
md_tibble <-
  all_md_str %>%
  purrr::map_dfr(parse_md)

## Output HTML file
generate_scroll_doc(path = "examples/parallaxr-examples-output.html",
                    inputs = md_tibble)
````
It took me until the fourth parallax to realize that the HTML files in the folder examples/Markdown were messing up that first line of code. R was trying to parse the HTML as a markdown and got stuck, which was problematic. The solution, once I realized the issue, was to delete or move the HTML files out of that folder. 

# Customizable?

I was able to solve the HTML files messing up the tibble, but most of the other issues I encountered in parallax weren't so easy, which is why I ended up deciding to not use it.

I'm still not entirely sure how the parallaxr functions specifies the parameters, as it includes no style.css file. But there were definitely behind-the-scenes formatting guidelines. For example, the pictures within the parallax could only be on the left or right. There was no 'none' option to make it full screen. Even more annoyingly, the html interactive widgets (such as my prized interactive leaflet!) only worked when the image was on the right. Widgets suddenly became static when the picture was on the left. 

# Conclusion

As I mentioned earlier, Randy and I decided in the end to scrap the parallax. While it was a difficult decision due to the amount of time and aggravation I spent on this project, it was the right decision so I can focus on a more intuitive, customizable format that has more of the kinks worked out. 
