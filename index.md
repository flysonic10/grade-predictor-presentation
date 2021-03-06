---
title       : Predicting Final Grade for Developing Data Products
subtitle    : 
author      : William Wnekowicz
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Overview

The Developing Data Products course on Coursera has four assignments: 3 quizzes and 1 course project.

The assignments contribute to the final grade as follows:

- Quiz 1 - 20%
- Quiz 2 - 20%
- Quiz 3 - 20%
- Course Project - 40%

Furthermore, the course syllabus outlines the following grading thresholds:

- >= 70% - Passing
- >= 90% - Passing with Distinction

---

## Goals

Our goals are to:
  1. Build an application to help students predict their Course Project scores
  2. Using known scores and the predicted score, report the final predicted grade for the class
  3. Report whether the final grade is passing and, if so, whether it merits distinction

---

## Prediction Model and Calculations

Our prediction model averages the known quiz scores and using simple multiplication, predicts the Course Project score to be 10% higher.


```r
totalQuizScores <- 80 + 90 + 100
prediction <- totalQuizScores / 3 * 1.10
prediction
```

```
## [1] 99
```

Final grades are then estimated using this prediction and the formula:

```r
finalGrade <- totalQuizScores / 3 * 0.6 + prediction * 0.4
finalGrade
```

```
## [1] 93.6
```

---

## Going further

As a proof of concept, the application currently uses a simple and naive method of estimating course project scores. 

A more complex model may be built by:
- Collecting data of student scores from past courses
- Fitting a Random Forests or stacked model based on quiz scores
- Repacing the current prediction function with a new prediction function based on the statistical model

## Resources

### Github Repository - https://github.com/flysonic10/grade-predictor

### Demo - https://will.shinyapps.io/grade-predictor




