---
title: "How to create sub labels like Gene Ontology graph with Ggplot"
collection: informatics
type: ""
permalink: /informatics/2017-04-25-ggplot-sub-labels
venue: ""
date: 2017-04-24
---

Reconstructable example for create sub labels like Gene Ontology graph with Ggplot

``` library(ggplot2)
library(grid)

# Use cars data from mpg dataset
g1 <- ggplot(data = mpg, aes(class)) +
  geom_bar() +
  theme(line = element_blank(), axis.text.x=element_blank()) +
  ggtitle("Boring plot but maaaarvelous labels")

# to increase the bottom margin
g2 <- g1 + annotate("text", x = 4, y = -20, label = "") 
  

# Create the text Grobs
Text1 = textGrob("Little cars")
Text2 = textGrob("Mid cars")
Text4 = textGrob("Big cars")


# Draw the plot
p1 = g2 + annotation_custom(grob = Text1,  xmin = 1, xmax = 2, ymin = -18, ymax = -18) +
          annotation_custom(grob = linesGrob(), xmin = 1, xmax = 2, ymin = -16, ymax = -16) +
          annotation_custom(grob = linesGrob(), xmin = 1, xmax = 1, ymin = -15, ymax = -16) +
          annotation_custom(grob = linesGrob(), xmin = 2, xmax = 2, ymin = -15, ymax = -16) +

          annotation_custom(grob = Text2,  xmin = 3, xmax = 4, ymin = -18, ymax = -18) +
          annotation_custom(grob = linesGrob(), xmin = 3, xmax = 4, ymin = -16, ymax = -16) +
          annotation_custom(grob = linesGrob(), xmin = 3, xmax = 3, ymin = -15, ymax = -16) +
          annotation_custom(grob = linesGrob(), xmin = 4, xmax = 4, ymin = -15, ymax = -16) +
  
          annotation_custom(grob = Text4,  xmin = 5, xmax = 7, ymin = -18, ymax = -18) +
          annotation_custom(grob = linesGrob(), xmin = 5, xmax = 7, ymin = -16, ymax = -16) +
          annotation_custom(grob = linesGrob(), xmin = 5, xmax = 5, ymin = -15, ymax = -16) +
          annotation_custom(grob = linesGrob(), xmin = 7, xmax = 7, ymin = -15, ymax = -16) +

          annotate(geom = "text", x = 0.8, y = -6, label = "2seater", color = "blue", angle = 45) +
          annotate(geom = "text", x = 1.8, y = -6, label = "compact", color = "blue", angle = 45) +
          annotate(geom = "text", x = 2.8, y = -6, label = "midsize", color = "blue", angle = 45) +
          annotate(geom = "text", x = 3.8, y = -6, label = "minivan", color = "blue", angle = 45) +
          annotate(geom = "text", x = 4.8, y = -6, label = "pickup", color = "blue", angle = 45) +
          annotate(geom = "text", x = 5.8, y = -8, label = "subcompact", color = "blue", angle = 45) +
          annotate(geom = "text", x = 6.8, y = -5, label = "suv", color = "blue", angle = 45) 
p1
```