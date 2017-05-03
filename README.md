# Assignment2
## My function will return the inverse matrix basing on the arguments.
## If the inverse matrixs have been cached, the function will directly
## return the cached value and will not recalculate it.

## The following functions return a specified matrix, which is a 
## list acutally. This function can be used to save the inverse matrix.

makeCacheMatrix <- function(x = matrix()) {
  inversematrix<-NULL
  set<-function(y){
    x<<-y
    inversematrix<<-NULL
  }
  get<-function() x
  setinverse<-function(inversem) inversematrix<<-inversem
  getinverse<-function() inversematrix
  list(set=set,get=get,setinverse=setinverse,getinverse=getinverse)
}


## This function can return the inverse matrix. Firstly it will 
## check whether the inverse matrix has been cached. If not, the
## function will calculate the inverse matrix and return it.

cacheSolve <- function(x, ...) {
  i<-x$getinverse()
  if(!is.null(i)){
    message("getting cached inversematrix")
    return(i)
  }
