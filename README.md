# R-Programming-Assignment-2
Coursera Week 3 peer-graded Assignment: Programming Assignment 2: Lexical Scoping

> ##The following pair of functions are used to create an object to store a matrix and caches its inverse.
> 
> ##Function 1 creates a special matrix object that can cache its inverse.
> 
> makeCacheMatrix<-function(x=matrix()){
+ inv<-NULL
+ set<-function(y){
+ x<<-y
+ inv<<-NULL
+ }
+ get<-function()x
+ setInverse<-function(inverse)inv<<-inverse
+ getInverse<-function()inv
+ list(set=set,
+ get=get,
+ setInverse=setInverse,
+ getInverse=getInverse)
+ }
> 
> ##Function 2 computes the inverse of the above matrix.It should retrieve the inverse from the cache, if the inverse has already been calculated.
> 
> cacheSolve<-function(x,...){
+ ##Return a matrix that is the inverse of 'x'
+ inv<-x$getInverse()
+ if(!is.null(inv)){
+ message("getting cached data")
+ return(inv)
+ }
+ mat<-x$get()
+ inv<-solve(mat,...)
+ x$setInverse(inv)
+ inv
+ }
