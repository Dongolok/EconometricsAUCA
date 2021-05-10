---
sort: 1
---

# Basics of R

Some materials are taken from the book “Hands-On-Programming With R” by Garrett Grolemund and online course on Coursera “Statistics with R”

## Objects

R lets you save data by storing it inside an R object. What’s an object? Just a name that you can use to call up stored data. For example, you can save data into an object like a or b. Wherever R encounters the object, it will replace it with the data saved inside, like so:

You can store numbers in objects, assume that you are paying 300$ for particular month in gas bills.

```
gas <- 300
gas
```
```
## [1] 300
```

Then suddenly fees are decreased.

```
gas <- 200
gas
```
```
## [1] 200
```

Assume that you are also paying for your groceries. Lets compute total expenditures in the month

```
groceries <- 2000
groceries
```
```
## [1] 2000
```
```
total = gas + groceries
total
```
```
## [1] 2200
```

You can also, store text data in objects. Text data should be in quotes.
```
name <- "Aibek"
```
You can see which object names you have already used with the function ls()
```
ls()
```
```
## [1] "gas"       "groceries" "name"      "total"
```

## Naming conventions

You can name an object in R almost anything you want, but there are a few rules. First, a name **cannot** start with a number. Second, a name cannot use some special symbols, like ^, !, $, @, +, -, /, or *.

## Sequence of numbers (Vectors)

### Continious sequence of numbers 

Objects can also store sequence of numbers. Assume that you have Alex, John, Sam. And their respecive ages are 18,19,20. You can store their ages in the object _ages_.

```
ages <- 18:20
ages
```
```
## [1] 18 19 20
```

### Discrete sequence of numbers

Assume that Alex, John and Sam are respecitvely 17, 23, 25 years old. In the case when we have discrete set of numbers, we can still store this numbers in the object. To do that we need to use special operator __c()__. For example, 
```
ages <- c(17, 23, 25)
ages
```
```
## [1] 17 23 25
```
One can remember usefull mnemonic to remember __c()__ operator as first letter for the word __column__. Basically, when we use operator __c()__ we created one column from spreadsheet by the name __ages__. 

| ages   |
| ------- | 
| 17 | 
| 23 | 
| 25 | 

R uses fancy name for columns, they are called vectors. So it is safely assume, that vectors are just columns of a spreadsheet.

In the same manner, we can create the column of names.
```
names <- c("Alex", "John", "Sam")
```

| names  |
| ------- | 
| Alex | 
| John | 
| Sam | 

## Dataframes
What is dataframe? Data is nothing more than just the spreadsheet.
To create dataframe we can use command _Data.Frame()_. Inside of the round brackets we need to supply columns, from which our dataframe will consist. For example, let us create dataframe of names and ages of people.

```scss
ages <- c(17, 23, 25)
names <- c("Alex", "John", "Sam")
df <- Data.Frame(names, ages)
df
```
We will have output as, 

| names   | ages     |
| ------- | -------- | 
| Alex    | 17       |
| John    | 23       |
| Sam     | 25       |

---

## Working with missing values in R
[Link to the notebook](https://www.kaggle.com/iliassuvanov/missing-values-in-r/edit)


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



### Number of missing values in each column
To check how much each column contains missing values, you can execute command, with supplied name of your dataframe.
_colSums(is.na(YOUR_DATAFRAME))_


```R
colSums(is.na(df))
```

```
names:0 wages:1 ages:2
```


We can see that there is 0 missing values in the column names. One missing value in the column wages and two missing values in the column ages.

### Doing statistics with missing values.
You can use statistical function in your code, even if your column has missing values, however you need explicetly state to your function, that you have missing values.


```R
mean(df$ages)
```

```
# NA
```

When we applied mean function to the column df\\$ages we got _<NA>_ as output. This happens, becaues we have missing values in our column df\$ages. We need to omit missing values, we can do that by specifying command,


```R
mean(df$ages, na.rm = TRUE)
```

```
# 26
```




