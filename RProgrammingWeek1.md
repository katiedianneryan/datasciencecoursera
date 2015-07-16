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

> [1] "integer"
 
> as.numeric(x)

> [1] 0 1 2 3 4 5 6
 
> as.logical(x)

> [1] FALSE TRUE TRUE TRUE TRUE TRUE TRUE
 
 > as.character(x)
 
> [1] "0" "1" "2" "3" "4" "5" "6"
 
 
* nonsensical coercion results in *NA*
* lists are important because they can hold different kinds of classes of data

##Matrices
* vectors with a dimernsion attribute
* dimension attribute is an interger vector of length 2 (nrow, ncol)
 

> m <- matrix(nrow=2, ncol=3)

> m 

>    [,1] [,2] [,3]
    
> [,1] NA   NA    NA

> [,2] NA   NA    NA


> dim(m)

>  [1] 2 3 ##The first interger is the number of rows, the second is the number of columns
  

> attributes(m)

>  $dim
 
>  [1] 2 3


* matrices are construbed column-wise, entries start in the upper left and run down the columns

> m <- matrix(1:6, nrow=2, ncol=3)

> m 

>    [,1] [,2] [,3]

> [,1] 1    3     5

> [,2] 2    4     6


* can create a matrix out of a vector by assigning it a dimension attribute

> m <- 1:10

>m
 
 > [1] 1 2 3 4 5 6 7 8 9 10

> dim(m) <- c(2, 5)

> m 

>     [,1] [,2] [,3] [,4] [,5]

> [,1] 1    3     5   7     9

> [,2] 2    4     6   8     10


* can also create a matrix through the functions cbind() and rbind()

 
> x <- 1:3

> y <- 10:12

> cbind(x, y)

>        x y

>  [1,]  1 10

>  [2,]  2 11

>  [3,]  3 12


*rbind combines them as rows instead of columns

##Factors
* two types: ordered or unordered
* think of it as an interger vector where each integer has a label
* factors are treated specially by modelling functions like lm() and glm()
* Using factos with labels is better than using integers because factors describe themselves (ie Male and Female rather than 1 and 2 [especially because someone else might not realize that other integers cannot be used in that column, there is no 6 in gender])
*  factor(c("yes", "yes", "no", "yes", "no))
* you can make a table out of the factor vector to see how many of each factor there are - table (x)
* R automatically makes the factor that is the first in the alaphabet the baseline level (no) and the other is the second level (yes)
*   You can change this with the arguments levels = c("yes", "no")

##Missing Values
* denoted by NA or NaN
* to test if something is a missing value you can use is.na() or is.nan()
* NaN is considered NA, but NA is not NaN (keep his in mind?)

##Data Frames
* Used to store tabular data
* a special type of list where every element of the list has the same length (BUT NOT NECCESSARILY SAME CLASS)
* Every row has a row.names
* Data frams are usually created by calling read.table() or read.csv()
* You can also convert it to a matrix (which only allows one type of class) by calling data.matrix()
* data.frame() can also create a data frame

> x <- data.frame(foo=1:4, bar+c(T, T, F, F))

> x

>    foo   bar

>  1   1   TRUE

>  2   2   TRUE

>  3   3   FALSE

>  4   4   FALSE

> nrow(x)

>  [1] 4

> ncol(x)

>  [1] 2


##Names Attributes
* can add names to each element of a vector

> x <- 1:3

> names(x)

>  NULL


> names(x)<- c("foo", "bar", "norf")

> x

>  foo   bar   norf

>    1     2     3

> names(x)

>  [1] "foo" "bar" "norf"

* lists can have names x<-list(a=1, b=2, c=3) gives the names a, b, c to the elements
* matrices can have names (dim names)
  * dimnames(m) <- list(c("a", "b"), c("c", "d") makes the rows a and b and the columns c and d

##Reading Tabular Data
* read.table, read.csv - read text files that contain data in rows& columns are converted in to a data frame in R
* readLines - reads a text file line by line
* source - reads R code for example functions or files
* dget - reads R codes files that have been deparsed
* load & unserialize are for binary functions
* writing data can be done with
  * write.table
  * writeLines
  * dump
  * dput
  * save
  * serialize
* arguments of the read.table function
  * file (the name of a file or connection)
  * header (logical indicating if the file has a header line - if the first line is titles say TRUE)
  * sep (a string indicating how the columns are separated - commas, semicolons, tabs, spaces, etc)
  * colClasses (a character vector indicating the class of each column in the dataset
  * nrows (number of rows in the dataset)
  * comment.char (a character string indicating the comment character other than # if you want)
  * skip (the number of lines to skip from the beginning)
  * stringsAsFactors (should character variables be coded as factors? = TRUE or FALSE)
* Can usually read.table without specifying any other arguments
* read.csv is identical to read.table except that .csv thinks the default separator is a comma (and that header is TrUE), .table default separator is a space

##Reading Large Tables
* To make your life easier and avoid R choking on large tables use this (and the read.table help file in R)
* Make sure your computer has enough RAM to run the table
* set comment.char="" (unless you have a specific comment character)
* USE the colClasses argument so that R doesn't have to figure this out on its own
  * If you have a few columns you can do this yourself
  * same if all columns are the same class (ie colClasses = "numeric")
  * If not, you can use this to have R figure it out based on the first 100 rows and then apply it to the original
 

  > initial <- read.table("datatable.txt", nrows = 100)
 
  > classes <- sapply(initial, class)
 
  > tabAll <- read.table("datatable.txt", colClasses = classes)


  * set nrows (overestimation is okay, won't make it faster but does help with memory usage)
* to estimate how much memory is required to store the dataset multiply rows x columns (to get how many items are in the dataframe) if they are all the same (ie numeric) multiply that number by the bytes (8 bytes/numeric) divide by 2^20 (to get MB)divide that again by 2^10 to get GB (you need about twice as much as this says to do all the extra processing)

##Textual Data Formats
* dump and dput can input textual data
* Unlike writing out a table or csv file, dump and dput preserve the metadata of the original
* textual formats are good for storing data because they can be editable (even if something gets corrupted)
* textual formats are also good for tracking changes between documnts (like subversion or git)
* Problem with textual formats are not very space efficient
* if you dput a data frame you can find out all the classes, names, structure, etc. (it makes it's own R code to show you all of this so that you can reconstruct the file)
* dget can only be used on one object, dump can be used on multiple

##Interfaces to the Outside World
* data are read using connection interfaces, connections can be made to files (most common) or to other, more exotic, things.
  * file (opens a connection to a file)
  * gzfile (opens a connection to a file compressed with gzip)
  * bzfile (opens a conection to a file compressed with bzip2)
  * url (opens a connection to a webpage) 

> string(file)
 
>  function (description = "", open = "", blocking = TRUE, encoding = getOption("encoding"))

  * description is the name of the file
  * open is a code indicating:
    * "r" read only
    * "w" writing (and initializing a new file)
    *  "a" appending
    *  "rb", "wb", "ab" reading, writing, or appending in binary mode (windows)
  *  these connections are more sophisticated than having to read an entire dataframe
  *  doing something like:
    con <- file("foo.txt", "r")
    data <- read.csv(con)
    close(con)
  is the same as 
    data <- read.csv("foo.txt)
  however, if you only want to read part of that file you could
    con <- file("foo.txt", "r")
    data <- readLines(con, 10)
    *prints out the first 10 lines*
  * use this to read the lines of code from a url - 

##Subsetting R Objects: Basics
* There are different ways to extract subsets of R objects
  * [ always returns an object of the same class as the original, can be used to select more than one element
  * [[ is used to extract elements of a list or a dataframe, can only be used to extract a single element and the clas of the returned object will not necessarily be a list or a dataframe
  * $ is used to extract elements of a list or dataframe by name, semantics are similar to that of [[

##Subsetting R Objects: Lists

> x <- list(foo=1:4, bar=0.6)

> x[1] ##This returns a list because the single bracket always returns the same class as the original

>  $foo

>  [1] 1 2 3 4


> x[[1]] ##This is just the sequence rather than a list
 
 > [1] 1 2 3 4
 
  
> x$bar ##This gives the element associated with the name "bar"

>  [1] 0.6

> x[["bar"]] ##This is basically the same

>  [1] 0.6

> x["bar"] ##This gives the list with the element including what you requested

>  $bar

>  [1] 0.6

* the [[ operator can be computed with indices - $ can only be used with literal names
  * ie, if you made name <- "foo" you could [[name]] and it would return those associated with foo, but $name would return NULL 

##Subsetting R Objects: Matrices
* by using [row index, column index]
* you don't always need both indices, you can say [row index, ] and it will give you all of the row indicated
* by default when a single element of a matrix is retrieved it is returned as a vector of length 1 rather than a 1x1 matrix. You can turn this off by setting drop=FALSE

##Subsetting R Objects: Partial Matching
* can identify with [[ and $

> x <- list(aardvark = 1:5)

> x$a

>  [1] 1 2 3 4 5

> x[["a"]]

>  NULL

> x[["a", exact=FALSE]]

>  [1] 1 2 3 4 5

##Removing NA Values

> x <- c(1, 2, NA, 4, NA, 5)

> bad <- is.na(x)


> bad

>  FALSE FALSE TRUE  FALsE  TRUE  FALSE


> x[!bad]

>  [1] 1 2 4 5

* complete.cases(x,y) only takes the cases where there are no missing values in a row
