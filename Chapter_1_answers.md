Chapter 1 Sample Answers
================
Justin Touchon
7/19/2021

This page provides sample answers to the assignment at the end of
Chapter 1 of Applied Statistics with R: A Practical Guide for the Life
Sciences by Justin Touchon. Since the assignment is very open-ended,
these answers are truly meant to be *examples* and are not the only
answers you can get. My hope is that you are here either because 1) you
want to check the answers you got to make sure you completed the
assignments correctly, or 2) you got stumped and need some help. Either
way, you will learn much more if you have already spent some time
working through the assignments on your own. If you haven’t done that,
close this page and go work on it! :)

<span style="color: #009933;">

# Assignment 1

**Create a data frame that contains at least one factor with three
categories and at least three columns of made up numeric data. Thus, it
should have at least four columns. Make sure the columns have meaningful
names. Have at least 10 rows per categories (i.e., at least 30 rows
long).**

</span>

How should you go about doing this? As with anything in R, there are of
course many different ways. I will show you how I would do it. The basic
idea here is to make a data frame with four columns and one of those
columns needs to be a factor with three categories.

Let’s start by making the factor. Since the data this book will be
working with are ecological data about red-eyed treefrog tadpoles, I
will stick with that general genre of data. Let’s imagine our three
categories are three different species of treefrogs. Let’s choose
hourglass treefrogs (the species pictured on the cover of the book),
which we will abbreviate “HGTF”, red-eyed treefrogs, which will be
“RETF”, and Rosenberg’s gladiator frog, or “GLDF”.

<div class="figure">

<img src="https://github.com/jtouchon/Applied-Statistics-with-R/blob/master/Treefrog_collage_small.png" alt="Three beautiful treefrogs from Central America. Photos by Justin Touchon." width="100%" />

</p>

</div>

In order to make our factor, we can combine the functions **rep()** and
**c()**. Each species abbreviation is repeated 10 times, and those
vectors are concatenated together to make a single vector.

``` r
#We first create our vector of species codes
species<-c(rep("HGTF",times=10), rep("RETF",times=10), rep("GLDF",times=10))
#By typing in the name of the vector, we can verify that it worked
species
```

    ##  [1] "HGTF" "HGTF" "HGTF" "HGTF" "HGTF" "HGTF" "HGTF" "HGTF" "HGTF" "HGTF"
    ## [11] "RETF" "RETF" "RETF" "RETF" "RETF" "RETF" "RETF" "RETF" "RETF" "RETF"
    ## [21] "GLDF" "GLDF" "GLDF" "GLDF" "GLDF" "GLDF" "GLDF" "GLDF" "GLDF" "GLDF"

If we want to specify that this should be a factor, we can do so with
the **as.factor()** function. Just assign the object over itself, as is
shown below.

``` r
species<-as.factor(species)
#Type the name of the object at the console to see the difference from the original version
species 
```

    ##  [1] HGTF HGTF HGTF HGTF HGTF HGTF HGTF HGTF HGTF HGTF RETF RETF RETF RETF RETF
    ## [16] RETF RETF RETF RETF RETF GLDF GLDF GLDF GLDF GLDF GLDF GLDF GLDF GLDF GLDF
    ## Levels: GLDF HGTF RETF

Next, we need to make our numeric variables. Perhaps our experiment
involves raising these tadpoles under three different conditions. For
the sake of example, let’s imagine that we raised them under three
different diets, which we will just call “control”, “dietA”, and
“dietB”. You could imagine that the control is what we always feed our
tadpoles, but diets A and B are experimental diets that we are
interested in understanding the effects of. Let’s also imagine that the
two experimental diets are most beneficial to a particular species.

Let’s create three numeric variables, one for each diet. Like above, we
need to concatenate together (using the **c()** function) three vectors
of numbers. We will create those numbers using the **rnorm()** function,
which creates a vector of numbers randomly selected from a normal
distribution with a given mean and standard deviation. If that doesn’t
make a lot of sense, don’t worry, the normal distribution will be
discussed in Chapter 3! Lastly, note that hourglass treefrog tadpoles
are considerably smaller than either red-eyed treefrog or gladiator frog
tadpoles, which are pretty similar in size.

``` r
#First, create a vector of total lengths measured from our hypothetical control diet. 
control<-c(rnorm(n=10, mean=20, sd=1), rnorm(n=10, mean=35, sd=1), rnorm(n=10, mean=35, sd=1))
#Next, we will create a vector of total lengths measured from our hypothetical experimental diet A.  
#Let's imagine that this diet really benefits the red-eyed treefrog tadpoles, which are the second set of 10 animals in our data frame.
dietA<-c(rnorm(n=10, mean=20, sd=1), rnorm(n=10, mean=45, sd=1), rnorm(n=10, mean=35, sd=1))
#Lastly, let's create a vector of total lengths measured from our hypothetical experimental diet B.  
#Let's imagine that this diet most benefits the gladiator frog tadpoles, which are the third set of 10 animals in our data frame.
dietB<-c(rnorm(n=10, mean=20, sd=1), rnorm(n=10, mean=35, sd=1), rnorm(n=10, mean=50, sd=1))
#We can see that these worked if we type the names of the vectors into the console.
control
```

    ##  [1] 19.36886 20.30410 19.59616 18.84679 19.85636 19.66399 19.28138 19.66268
    ##  [9] 20.26739 19.59236 34.09966 35.97409 34.72731 34.22270 33.72508 35.05375
    ## [17] 36.63770 35.61648 35.92626 36.58228 33.56128 33.94041 35.48072 35.64967
    ## [25] 35.48198 35.30177 36.43902 35.43321 34.69697 35.09598

``` r
dietA
```

    ##  [1] 22.76725 19.56477 17.78819 22.21105 21.29635 20.76063 18.11092 18.93406
    ##  [9] 19.24611 19.86906 46.43693 47.47193 47.62666 46.44623 44.93318 46.40193
    ## [17] 44.50653 43.84873 44.89711 45.20338 35.04895 35.28896 35.32795 34.31560
    ## [25] 34.35393 34.66298 36.15109 34.69683 36.56437 35.71103

``` r
dietB
```

    ##  [1] 19.79134 19.31878 19.81408 20.85179 18.65275 20.25175 21.70913 20.04325
    ##  [9] 20.00092 19.29106 35.49950 35.27609 35.61221 35.67295 35.31574 36.20073
    ## [17] 36.86884 35.90400 35.73951 34.42973 48.45875 49.68041 47.50246 49.55723
    ## [25] 50.37731 48.94015 50.09736 48.89057 50.37282 50.42478

Okay, now we have our four vectors. It’s time to combine them into a
data frame using the function **data.frame()**. Remember to assign your
new data frame to an object!

``` r
tad_data<-data.frame(species, control, dietA, dietB)
tad_data
```

    ##    species  control    dietA    dietB
    ## 1     HGTF 19.36886 22.76725 19.79134
    ## 2     HGTF 20.30410 19.56477 19.31878
    ## 3     HGTF 19.59616 17.78819 19.81408
    ## 4     HGTF 18.84679 22.21105 20.85179
    ## 5     HGTF 19.85636 21.29635 18.65275
    ## 6     HGTF 19.66399 20.76063 20.25175
    ## 7     HGTF 19.28138 18.11092 21.70913
    ## 8     HGTF 19.66268 18.93406 20.04325
    ## 9     HGTF 20.26739 19.24611 20.00092
    ## 10    HGTF 19.59236 19.86906 19.29106
    ## 11    RETF 34.09966 46.43693 35.49950
    ## 12    RETF 35.97409 47.47193 35.27609
    ## 13    RETF 34.72731 47.62666 35.61221
    ## 14    RETF 34.22270 46.44623 35.67295
    ## 15    RETF 33.72508 44.93318 35.31574
    ## 16    RETF 35.05375 46.40193 36.20073
    ## 17    RETF 36.63770 44.50653 36.86884
    ## 18    RETF 35.61648 43.84873 35.90400
    ## 19    RETF 35.92626 44.89711 35.73951
    ## 20    RETF 36.58228 45.20338 34.42973
    ## 21    GLDF 33.56128 35.04895 48.45875
    ## 22    GLDF 33.94041 35.28896 49.68041
    ## 23    GLDF 35.48072 35.32795 47.50246
    ## 24    GLDF 35.64967 34.31560 49.55723
    ## 25    GLDF 35.48198 34.35393 50.37731
    ## 26    GLDF 35.30177 34.66298 48.94015
    ## 27    GLDF 36.43902 36.15109 50.09736
    ## 28    GLDF 35.43321 34.69683 48.89057
    ## 29    GLDF 34.69697 36.56437 50.37282
    ## 30    GLDF 35.09598 35.71103 50.42478

Hooray, you did it! As discussed earlier, you could choose anything to
be your categories (e.g., strains of mice in a study, brands of cereal
to eat, species of plants) and anything for your numeric variables
(e.g., responses of mice to different tests, sugar, protein, and fat
content of cereals, growth rates of plants under three different light
conditions, etc.) Okay, onward and upward.

<span style="color: #009933;">

# Assignment 2

**Once you have a data frame, plot a histogram of your numeric
variables. Try to dress it up by adding color, changing the limits of
the axes, and adding a main title. How will you figure out how to do
that? Look at the help file for** hist()**.**

</span>

The basic goal here is to look at the values in your numeric vectors. If
you look at the help file for the **hist()** function (which can be done
by simply typing *?hist* in the console) you will see there are lots and
lots of options. All of those are *optional* except for *x*, which is
the vector of values you want to plot. In our data frame, we can access
our numeric vectors with the **$** operator. For example, if we want to
plot a histogram of the vector of sizes we measured in our control diet,
we can type the following:

``` r
hist(tad_data$control)
```

![](Chapter_1_answers_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

If you do that, you might get something very unhelpful, like I have
here. In a function like **hist()**, R is going to try to choose a set
of divisions in the data which it *thinks* will be most useful, but we
can override them. Here, we want to set the number of *breaks* to use
when plotting the histogram. Let’s go with 20 and see what that looks
like.

``` r
hist(tad_data$control, breaks=20)
```

![](Chapter_1_answers_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

We can see a cluster of data representing our smallest species and a
larger cluster o values representing the two larger species. You should
also notice that by default R names our x-axis the variable we provided
it. We can customize that by specify a new *label* for our x-axis, with
the *xlab=* argument. We can also add color with the *col=* argument.
Below, I’ve picked the color “seagreen” but you could of course pick
whatever you want. (hint: type **colors()** in the console)

``` r
hist(tad_data$control, breaks=20, xlab="Sizes of hypothetical tadpoles (mm)", col="seagreen")
```

![](Chapter_1_answers_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

There are lots of other ways to dress up a figure. Play around with
changing the title with the *main==* argument, or play with the range
limits using *xlim=* or *ylim=*. You can even *add* one histogram to an
existing plot, using the *add=T* argument.

<span style="color: #009933;">

# Assignment 3

**Use the** plot() **function to try and plot your numeric and
categorical variables. What happens when you give R different types of
data to plot?**

</span>

The **plot()** function is a very basic and fundamental function in R.
We will explore its utility in the coming chapters, but for now let’s
explore what happens when we give it just a single vector of numbers.
For example, if we provide **plot()** with our factor variable “species”
it will plot a bar for each category with the height of the bar being
now many observations are in each category. In this case, that means
three bars that are each 10 high.

``` r
plot(tad_data$species)
```

![](Chapter_1_answers_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

What happens if we provide a vector of numeric values? R will plot each
of the values in our vector on the y-axis, with the x-axis being the row
of value. Thus, **plot()** just starts at the first row of the data
frame and proceeds downward. In the figure below, the first 10 values
(which correspond to our HGTF animals, which were the smallest) are
smaller than values 11–30, which correspond to the two larger species.

``` r
plot(tad_data$control)
```

![](Chapter_1_answers_files/figure-gfm/unnamed-chunk-10-1.png)<!-- -->

In the coming chapters we will explore what happens if you provide
combinations of vectors as the x- and y-values, and we will begin
learning how to use the ***ggplot2*** package to make beautiful figures.
However, for now that’s it! Great job.
