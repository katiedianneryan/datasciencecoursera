#Week Two
###Learning Objectives
By the end of this week you should be able to:
- Write an if-else expression
- Write a for loop, a while loop, and a repeat loop
- Define a function in R and specify its return value [see Functions Part 1 and Part 2]
- Describe how R binds a value to a symbol via the search list
- Define what lexical scoping is with respect to how the value of free variables are resolved in R
- Describe the difference between lexical scoping and dynamic scoping rules
- Convert a character string representing a date/time into an R datetime object. [see Dates and Times]

##Introduction
- Control Structures control the flow of a program for when you are setting up a longer program to happen (not interactive as we have been), they include things like:
  1. if, else (test logical conditions)
  2. for (execute a loop a fixed number of times)
  3. while (executes a loop while a condition is true)
  4. repeat (allows to infinite loop)
  5. break (breaks out of any loop)
  6. next (goes to the next loop)
  7. return (exits a loop)

##If-Else
* If  logical conditions and makes the R program do something if it is True (if true then x)
* You can combine this with else if you want there to be an alternate option (or else, if false, y)
* You can also combine multiple conditions with else if (condition2)


    > if(x>3) {

        > y <- 10

    > } else {

        > y <- 0

    > }

OR YOU CAN ALSO DO THIS:


    > y <- if(x>3) {

      > 10

    > } else {

      > 0

    > }

* do not always need else function, can just test and have a single result

##For Loops
* most common type of loop
* loop index (typically called i, might be j, k, l, etc if you have multiple)


    > x <- c("a", "b", "c", "d")

    > for(i in 1:4) {    ##creates an index (i) of numbers 1 through 4

       > print(x[i])   ##prints the element of x that corresponds with the index

    > } 

OR YOU CAN ALSO DO THIS:


    > for(i in seq_along(x)) {    ##creates a integer sequence that is the same length as the vector x (doesn't require you to know the length)

        > print(x[i])

    > } 

OR YOU CAN ALSO DO THIS:


    > for(letter in x) {        ##takes values from the vector itself

        > print(letter)

    > } 

OR YOU CAN DO THIS ALSO:


    > for(i in 1:4) print(x[i])     ##if the for loop only has a single loop you don't actually need the curly brackets


* for loops can be nested (generally don't nest more than 2-3 levels, though, or it gets confusing fast)


    > x <- matrix(1:6, 2, 3)

    > for(i in seq_len(nrow(x))) {    ##loops over rows, then loops over columns

      > for(j in seq_len(ncol(x)))  {

        > print(x[i,k])

    > } 

* seq_len aka seq_lense the idea is that it takes an interger (aka the number of rows in x) and makes a sequence out of that

##While loops
* begins by testing a condition (like if/else) and then executes the loop
* once the loop is executed the condition is tested again and continues to run until it fulfils the conditions
 

    > count <- 0

    > while(count < 10) {

       > print(count)

            > count <- count+1

> }

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
