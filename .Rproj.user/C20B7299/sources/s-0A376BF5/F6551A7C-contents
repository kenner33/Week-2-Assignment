# A function that takes a directory of data files and a threshold for 
# complete cases and calculates the correlation between sulfate and nitrate for 
# monitor locations where the number of completely observed cases (on all 
# variables) is greater than the threshold. The function should return a 
# vector of correlations for the monitors that meet the threshold requirement. 
# If no monitors meet the threshold requirement, then the function should 
# return a numeric vector of length 0.

corr <- function(directory, threshold = 0) {
  id = 1:332
  files <- list.files(directory, full.names = 1)
  result <-vector(mode="numeric", length=0)
  
  for(i in seq(files)) {
    airquality <- read.csv(files[i])
    good <- complete.cases(airquality)
    airquality <- airquality[good, ]
    if (nrow(airquality) > threshold) {
      
      # We need [[]] around pollutant instead of [] since airquality["sulfate"]
      # is a data.frame but we need a vector here. Hence, [[]]. Please note that
      # using either [[]] or [] gives the same results as the test cases
      
      correlation <- cor(airquality[["sulfate"]], airquality[["nitrate"]])
      result <- append(result, correlation)
    }
  }
  result
}