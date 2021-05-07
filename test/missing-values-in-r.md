
# Working with missing values in R
[Link to the notebook](https://www.kaggle.com/iliassuvanov/missing-values-in-r/edit)

```R
# This R environment comes with many helpful analytics packages installed
# It is defined by the kaggle/rstats Docker image: https://github.com/kaggle/docker-rstats
# For example, here's a helpful package to load

library(tidyverse) # metapackage of all tidyverse packages

# Input data files are available in the read-only "../input/" directory
# For example, running this (by clicking run or pressing Shift+Enter) will list all files under the input directory

list.files(path = "../input")

# You can write up to 20GB to the current directory (/kaggle/working/) that gets preserved as output when you create a version using "Save & Run All" 
# You can also write temporary files to /kaggle/temp/, but they won't be saved outside of the current session
```


```R
names <- c("Alex", "John", "Michael", "Joe", "Wu")
wages <- c(30000, 25000, NA, 50000, 43000)
ages <- c(NA, 25, 23, 30, NA)
df <- data.frame(names, wages, ages)
```


```R
head(df)
```


<table class="dataframe">
<caption>A data.frame: 5 × 3</caption>
<thead>
	<tr><th></th><th scope=col>names</th><th scope=col>wages</th><th scope=col>ages</th></tr>
	<tr><th></th><th scope=col>&lt;fct&gt;</th><th scope=col>&lt;dbl&gt;</th><th scope=col>&lt;dbl&gt;</th></tr>
</thead>
<tbody>
	<tr><th scope=row>1</th><td>Alex   </td><td>30000</td><td>NA</td></tr>
	<tr><th scope=row>2</th><td>John   </td><td>25000</td><td>25</td></tr>
	<tr><th scope=row>3</th><td>Michael</td><td>   NA</td><td>23</td></tr>
	<tr><th scope=row>4</th><td>Joe    </td><td>50000</td><td>30</td></tr>
	<tr><th scope=row>5</th><td>Wu     </td><td>43000</td><td>NA</td></tr>
</tbody>
</table>



## Number of missing values in each column
To check how much each column contains missing values, you can execute command, with supplied name of your dataframe.
_colSums(is.na(YOUR_DATAFRAME))_


```R
colSums(is.na(df))
```


<style>
.dl-inline {width: auto; margin:0; padding: 0}
.dl-inline>dt, .dl-inline>dd {float: none; width: auto; display: inline-block}
.dl-inline>dt::after {content: ":\0020"; padding-right: .5ex}
.dl-inline>dt:not(:first-of-type) {padding-left: .5ex}
</style>

<dl class=dl-inline>
<dt>names</dt>
<dd>0</dd>
<dt>wages</dt>
<dd>1</dd><
dt>ages</dt>
<dd>2</dd>
</dl>



We can see that there is 0 missing values in the column names. One missing value in the column wages and two missing values in the column ages.

## Doing statistics with missing values.
You can use statistical function in your code, even if your column has missing values, however you need explicetly state to your function, that you have missing values.


```R
mean(df$ages)
```

```
NA
```

When we applied mean function to the column df\\$ages we got _<NA>_ as output. This happens, becaues we have missing values in our column df\$ages. We need to omit missing values, we can do that by specifying command,


```R
mean(df$ages, na.rm = TRUE)
```

```
26
```


