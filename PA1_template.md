# Reproducible Research: Peer Assessment 1

## Loading and preprocessing the data

```r
require(ggplot2)
```

```
## Loading required package: ggplot2
```

```
## Warning: package 'ggplot2' was built under R version 3.2.1
```

```r
DT <- read.csv(unz('activity.zip', 'activity.csv'))
DT$date <- as.Date(DT$date, '%Y-%M-%d')
```

## What is mean total number of steps taken per day?

```r
DT.steps <- data.frame(steps = tapply(DT$steps, DT$date, sum, na.rm = TRUE))

qplot(data = DT.steps, 
      DT.steps$steps, 
      breaks = seq(0, 35000, by = 5000),
      xlab = 'Nuber of Steps',
      ylab = 'Frequency', 
      main = 'Distribution of number of steps taken per day')
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png) 

```r
mean(DT.steps$steps)
```

```
## [1] 18406.71
```

```r
median(DT.steps$steps)
```

```
## [1] 20525
```

## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
