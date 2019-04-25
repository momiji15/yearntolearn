---
title: "About Me Template"
author: "Dorris Scott"
date: "4/23/2019"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
## Name 
If you want to insert a picture, I suggest you create an images file where you are storing your R Markdown document and put your image there. You can then refer to the location of your image by 
adding this code:
`![](images\mypic.jpg)`

## Program of Study
Also self-explanatory!

## Biography
Give people an idea of who you are in at least three sentences!

## Research Interests
- Can you list one?
- Can you list another one?
- Am I asking too much to list a third?

## Education
You know what to do.

## Hobbies
- Give me one!
- Who am I kidding, give me another!
- Do you have another hobby? Or am I asking too much again?

## Bonus
The below information was taken from the default information that pops up when you generate your R Markdown document. Notice how you can see the code under the Embedding Code Chunks section. 

## Embedding Code Chunks

```{r cars}
summary(cars)
```
If you want to see the actual code, you do not need to add `echo = TRUE` because it is the default setting.


## Including Plots

```{r pressure, echo=FALSE}
plot(pressure)
```

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
