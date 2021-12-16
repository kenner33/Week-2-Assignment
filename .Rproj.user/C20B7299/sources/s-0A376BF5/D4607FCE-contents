# 'complete' reads a directory full of files and reports the number of 
# completely observed cases in each data file. The function should return 
# a data frame where the first column is the name of the file and the second 
#column is the number of complete cases. 

complete <- function(directory, id = 1:332) {
  files <- list.files(directory, full.names = 1)
  comp_files <- data.frame(id=integer(), nobs=integer())
  for (i in 1:length(id)) {
    comp_files[i,1] <- id[i]
    comp_files[i, 2] <- sum(complete.cases(read.csv(files[id[i]])))
  }
  comp_files
}