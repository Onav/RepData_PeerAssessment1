# Reproducible Research: Peer Assessment 1

## Loading and preprocessing the data


```r
unzip("activity.zip")
activity <- read.csv("activity.csv")
```


## What is mean total number of steps taken per day?

```r
totalSteps<-aggregate(steps~date,data=activity, FUN = sum,na.rm=TRUE)
hist(totalSteps$steps, xlab = "Total Steps per day")
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png) 



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
