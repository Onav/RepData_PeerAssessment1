# Reproducible Research: Peer Assessment 1

## Loading and preprocessing the data

Unzip and load current data

```r
unzip("activity.zip")
activity <- read.csv("activity.csv")
```


## What is mean total number of steps taken per day?

Calculate total steps per day and look at distribution.

```r
totalSteps<-aggregate(steps~date,data=activity, FUN = sum,na.rm=TRUE)
hist(totalSteps$steps, xlab = "Total Steps per day")
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png) 

Calculate mean and median of total steps

```r
mean(totalSteps$steps)
```

```
## [1] 10766.19
```

```r
median(totalSteps$steps)
```

```
## [1] 10765
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
