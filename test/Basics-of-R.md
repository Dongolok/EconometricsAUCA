---
sort: 1
---

# Basics of R

Some materials are taken from the book “Hands-On-Programming With R” by Garrett Grolemund and online course on Coursera “Statistics with R”

# Objects

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

# Naming conventions

You can name an object in R almost anything you want, but there are a few rules. First, a name **cannot** start with a number. Second, a name cannot use some special symbols, like ^, !, $, @, +, -, /, or *.

# Sequence of numbers (Vectors)

## Continious sequence of numbers 

Objects can also store sequence of numbers. Assume that you have Alex, John, Sam. And their respecive ages are 18,19,20. You can store their ages in the object _ages_.

```
ages <- 18:20
ages
```
```
## [1] 18 19 20
```

## Discrete sequence of numbers

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




