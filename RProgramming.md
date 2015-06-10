#Week One
##Introduction
* *No notes*

##Overview and History of R
- R is a dialect of the older language S
- R is similar to S and share many semantic features
- R is great because it runs on any computer OS
- It's also Free code which means that people tend to be constantly working with, and improving the software, even I could!
- However, R has some negative sides as well, such as it's age (since it's based on S), and for the most part everything you want to work with must be in phyhsical memory

##R Console Input and Evaluation
* <- assigns an input
* 1:20 creates a series vector that includes every number from 1 through 20
* R has five basic "atomic" classes of object
  1. character
  2. numeric
  3. integer
  4. complex
  5. logical
* vectors only contain items of the same class
*   unless it's a list, which can contain items of different classes

##Objects and Attributes
* Vectors all have certain attributes
  *   names, dimnames
  *   dimensions
  *   class
  *   length
  *   user-defined data/emtadata
*   attributes can be accessed with the command attributes()

##Vectors and Lists
* c() can be used to combine
 

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

##
* 
* 
* 
