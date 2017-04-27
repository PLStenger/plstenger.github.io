---
title: "Boxplot of table using ggplot2"
collection: informatics
type: ""
permalink: /informatics/2017-04-27-ggplot-reshape-data
venue: ""
date: 2017-04-27
---

In `R`, `ggplot2` requires data in a specific format. So, if you want to create a box plot with `ggplot2` from a table, you must reshape it.

Data table example:

```   dats:       
X19d X7d X33g X30g X7d.1 X14d X26d X31d X5d X18d X31g X22d X4d X19g X34d X25d X13d X7d.2 X40g X27g X1d X11g X22g X37g X19d.1 X5g X30d X38g X28g X37g.1 X13g X4g
1     8   2    8    2     3    8    4    8   3    8    5    9   5    7    9    4    8     3    8    2   2    7    3    8      8   2    3    7    3      8    7   7
2     7   3    8    6     3    6    5    5   5    9    6    7   7    7    9    7    7     6    7    5   6    7    8    8      8   5    5    5    6      6    7   7
3     7   4    8    6     6    3    7    5   3    9    7    8   9    6    7    5    6     4    8    4   6    9    7    5      7   5    8    4    7      5    8   7
4     9   2    8    2     2    7    5    6   5    6    7    7   8    9    9    7    9     3    6    6   4   10    8    9      4   7    2    3    3      9    4   5
5     6   3    6    3     5    6    3    6   3    7    4    3   3    5    3    6    3     5    4    2   4    2    2    8      5   3    2    5    2      5    3   2
6     9   7    9    4     8    5    8    5   5    8    6    5   7    6    7    6    7     6    8    4   8    6    7    5      7   6    5    8    7      8    5   5
7     8   3    7    3     8    4    5    6   8    3    5    5   8    6    6    6    7     6    7    3   3    7    4    5      6   3    5    5    7      9    7   7
8     5   4    7    6     7    7    3    5   6    8    7    4   7    7    5    7    7     7    8    6   8    9    6    7      7   5    6    8    6      8    7   7
9     6   7    7    6     8    7    6    5   6    7    7    7   7    7    7    6    7     7    7    6   8    7    6    7      7   7    7    7    6      7    7   7
10    6   1    6    5     2    3    5    3   5    8    5    5   7    6    6    4    6     1    5    3   5    2    7    3      7   4    6    7    8      3    7   7
```

``` library(ggplot2)        
require(reshape2)       
ggplot(data = melt(dats), aes(x=variable, y=value)) + geom_boxplot(aes(fill=variable))
```


<br/><img src='/images/bp.png'>