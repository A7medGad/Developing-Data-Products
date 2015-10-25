---
title       : Guess the Number Project
subtitle    : 
author      : Ahmed Gad
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Guess the Number

1. The project is generating a random number.
2. The user trying to geuss the number.
3. If the entered number is higher, lower, correct, the system should interact accordingly.


--- .class #id 



## ui.R

in the ui.R file we user a varity of widgets, input and output textboxs, submit button.

--- .class #id 


## The servr.R

in the server.R file we use the function described later to generate a random number and check the input from the user.

--- .class #id 

## Main function.

The main function is descriped as below:


```r
numberGuessed <- function(guess, number) {
    returnValue <- "Nothing entered yet."
    if (guess > 100) {
        #print(guess)
        #print(class(guess))
        #print(class(100))
        returnValue <- 'Above 100.\nPlease make a selection between 1 and 100.'
    }
    else if (guess < 1) {
        #print(guess)
        returnValue <- 'Below 1.\nPlease make a selection between 1 and 100.'
    }
    else if (guess > number) {
        returnValue <- 'Higher than the number.'
    }
    else if (guess < number) {
        returnValue <- 'Lower than the number.'
    }
    else if (guess == number) {
        returnValue <- 'Correct!'
    }
    returnValue
}
```
