#Week One
###Learning Objectives
By the end of week 1 you should be able to:
- Install the R and RStudio software packages
- Download and install the swirl package for R
- Describe the history of the S and R programming lectures
- Describe the differences between atomic data types
- Execute basic arithmetic operations
- Subset R objects using the "[", "[[", and "$" operators and logical vectors
- Describe the explicit coercion feature of R
- Remove missing (NA) values from a vector

##Introduction
- *No notes*

##Overview and History of R
- R is a dialect of the older language S
- S was developed in Bell Labs by John Chambers
- 1988 v.3 is written which is more similar to what we have today
- The goal is to be able to use the S environment to look at data without being a programmer, but would hopefully transitioon into programming when they outgrew the current environment (organic/natural transition)
- R was created in New Zealand by Ross Ihaka and Robert Gentleman
- R is similar to S and share many semantic features
- R is great because it runs on any computer OS (and has a huge user/development community)
- It's also Free code which means that people tend to be constantly working with, and improving the software, even I could!
- Four basic freedoms of Free Software
- 0 - Freedom to run the program, for any purpose
- 1 - Freedom to study how the program works, and adapt it to your needs
- 2 - Freedom to redistribute copies so you can help your neighbour
- 3 - Freedom to improve the program and release improvements to the public so that the whole community benefits
- However, R has some negative sides as well, such as it's age (since it's based on S), and for the most part everything you want to work with must be in phyhsical memory
- Two sides of R - the base R system from CRAN and packages (about 4000 available on CRAN)
- http://cran.r-project.org is full of useful documents.

##R Console Input and Evaluation
* <- assigns an input
* 1:20 creates a series vector that includes every number from 1 through 20

##Objects and Attributes
* R has five basic "atomic" classes of object
  1. character
  2. numeric
  3. integer
  4. complex
  5. logical
* vectors only contain items of the same class
*   unless it's a list, which can contain items of different classes
*  If you want an interger (rather than simply numeric) apply to L suffix to the data (ie x <- 4L)
*  *inf* is infinity
*  *NaN* is not a number (undefined)
* R objects can all have certain attributes
  *   names, dimnames 
  *   dimensions *matrix with have multiple dimensions*
  *   class
  *   length *vector the length is the number of items in the vector*
  *   user-defined data/emtadata
*   attributes can be accessed with the command attributes()

##Vectors and Lists
* c() can be used to concatonate
 

> x <- c(0.5, 0.6) ## numeric

> x <- c(TRUE, FALSE) ## logical

> x <- c(T, F) ## logical

> x <- c("a", "b", "c") ## character

> x <- 9:29 ## integer

> x <- c(1+0i, 2+4i) ## complex


*You can also use vector() function to create a blank vector


> x <- vector("numeric", length = 10)
> x
 [1] 0 0 0 0 0 0 0 0 0 0


* If you're combining different elements to a vector it *coerces* them down (numbers become characters, logicals become numerics, etc.)
* you can explicitly coerce into a defined class with the function as.class


> x <- 0:6

> class(x)
 [1] "integer"
 
> as.numeric(x)
 [1] 0 1 2 3 4 5 6
 
> as.logical(x)
 [1] FALSE TRUE TRUE TRUE TRUE TRUE TRUE
 
 > as.character(x)
 [1] "0" "1" "2" "3" "4" "5" "6"
 
 
* nonsensical coercion results in *NA*
* lists are important because they can hold different kinds of classes of data

##Matrices
* vectors with a dimernsion attribute
* dimension attribute is an interger vector of length 2 (nrow, ncol)
 

> m <- matrix(nrow=2, ncol=3)
> m 
    [,1] [,2] [,3]
[,1] NA   NA    NA
[,2] NA   NA    NA

> dim(m)
  [1] 2 3 ##The first interger is the number of rows, the second is the number of columns

> attributes(m)
  $dim
  [1] 2 3


* 
* 
* 

##
* 
* 
* 

##
* 
* 
* 

##
* 
* 
* 

##
* 
* 
* 
