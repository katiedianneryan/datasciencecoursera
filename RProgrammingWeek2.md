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

* Be very careful. Improperly written while loops can result in infinite looping!
* You can test multiple conditions
* 

z <- 5

    while(z>=3 && z<=10) {
    print(z)
    coin <- rbinom(1, 1, 0.5)
    
    if(coin==1) {
        z <- z+1
    } else {
        z <- z-1
    }
}
  
##Repeat, Next, Break
* Repeat initiates an infinite loop (not commonly used)
* Break is the only way to exit this infinite loop
* Next is used in any looping construct when you want to skip iterations


    for(i in 1:100) {
    if(i <=20) {
      next
    }
    j<- i+1
    print(j)
  }
  
* Return signals that a function should exit and return a given value

##Your First R Function
* Write it in a text file
* see "yourFirstRFunction.r" in rStudio for other notes from thi section

##Functions
* stored as R objects
* functions in R are treated as "first class object" therefore you can use them just like other objects
* this includes passing functions to other fuctions as arguments or nesting 
* functions have *named arguments* which can have default values
  * *formal arguments* are those arguments included in the function definition
  * the **formals** function returns a list of all the formal arguments in a function
  * Not every function can in R makes use of all the formal argument
  * function arguments can be missing, or might have default values
* with arguments, it checks for an exact match for a named argument, then a partial match, then a positional match
* when you define a function you should name all of the arguments and set defaults (TRUE, FALSE, NULL) if appropriate
* arguments are only evaluated if it has to.
* the "..." argument - a variable number of elements that can be passed on to other functions - this is handy if you want t tweak a default function in r!
    myplot <- function(x, y, type = "1", ...) {
      plot(x, y, type=type, ...) }

 * make sure that anything after ... that you want changed much be naed explicitely
 
##Symbol Binding
* R automatically searches the environments in R for a symbol name matching the one requested
* If not, it searches the namespaves of each of the package on the search list
* You can see this with the search function

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
