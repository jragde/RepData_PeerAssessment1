# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

1. Load the data  


```r
if (!file.exists("activity.csv")){
  unzip(zipfile="activity.zip")
}  
data1 <- read.csv("activity.csv", sep = ",", colClasses = c("numeric", "Date", "numeric"))
```

2. Process/Transform the data


```r
data1$interval <- as.factor(data1$interval)
```

## What is mean total number of steps taken per day?

Calculate the mean total number of steps taken per day.  

```r
dailySteps <- aggregate(steps ~ date, data1, sum,na.rm=TRUE)
```

Create a histogram of the total number of steps taken per day.


```r
hist(dailySteps$steps, 
     col = "green",
     breaks = seq(from = 0, to = 27000, by = 1500),
     main = "Histogram of Daily Steps", 
     xlab = "Total Daily Steps",
     ylab = "Timer per day")
```

![](PA1_template_files/figure-html/histStepsPerDay-1.png)

## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
