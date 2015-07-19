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

Calculate mean steps per 5 min interval and plot time series.


```r
stepsInterval <- aggregate(steps ~ interval, data = activity, FUN = mean, na.rm = TRUE)
plot(steps ~ interval, data = stepsInterval, type = "l")
```

![](PA1_template_files/figure-html/unnamed-chunk-4-1.png) 

Which 5-minute interval, on average across all the days in the dataset, contains the maximum number of steps? (Starting at min #:)

```r
maxInterval <- stepsInterval[which.max(stepsInterval$steps),"interval"]
maxInterval
```

```
## [1] 835
```


## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
