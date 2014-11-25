---
title       : Power Analysis
subtitle    : 
author      : Issa Coulibaly
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Motivation

1. Power of correlation analysis 
2. Two samples of equal size
3. A given p value
4. Power for a range of r

--- .class #id 

## Workflow
1. User selects a p value
2. User selects a sample size
3. User can  view effect of varying sample size
4. Apllication displays power plot
5. Application displays a data frame

---
## Some R codes

```r
	r <- seq(.1,1,.02);nr <- length(r);
	pow<-vector("numeric",length=nr)
	for (i in 1:nr){
		result <- pwr.r.test(n = 25, r = r[i],
												 sig.level = 0.05, power = NULL,
												 alternative = "two.sided")
pow[i] <- result$power}
dat<-data.frame(r=r,power=pow)
head(dat)
```

```
##      r      power
## 1 0.10 0.07030750
## 2 0.12 0.08177267
## 3 0.14 0.09558669
## 4 0.16 0.11185618
## 5 0.18 0.13068496
## 6 0.20 0.15216625
```

---
## Output Power plot
![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.png) 
---
