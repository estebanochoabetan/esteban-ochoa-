# esteban-ochoa-
coursera
makeCourseraVector <- function(x = numeric()) {
  trl <- NULL # i change the variable inv to trl
  set <- function(y) {
    x <<- y
    trl <<- NULL
  }
  get <- function() x
  setInverse <- function(Texttrl) trl <<- mean #  the name of the  variable is Texttrl
  getInverse <- function() trl
  list(set = set, get = get,
       setmean = setmean,
       getmean = getmean)
}

cachemean <- function(x, ...) {
  m <- x$getmean()
  if(!is.null(m)) {
    message("getting cached data")
    return(m)
  }
  data <- x$get()
  m <- mean(data, ...)
  x$setmean(m)
  m
}
