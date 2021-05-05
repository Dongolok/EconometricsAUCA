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






Text can be anything **bold**, _italic_, or ~~strikethrough~~. [Links](https://github.com)  be blue with no underlines (unless hovered over).

There should be whitespace between paragraphs. There should be whitespace between paragraphs. There should be whitespace between paragraphs. There should be whitespace between paragraphs.

There should be whitespace between paragraphs. There should be whitespace between paragraphs. There should be whitespace between paragraphs. There should be whitespace between paragraphs.

> There should be no margin above this first sentence.
>
> Blockquotes should be a lighter gray with a gray border along the left side.
>
> There should be no margin below this final sentence.

# Header 1

This is a normal paragraph following a header. Bacon ipsum dolor sit amet t-bone doner shank drumstick, pork belly porchetta chuck sausage brisket ham hock rump pig. Chuck kielbasa leberkas, pork bresaola ham hock filet mignon cow shoulder short ribs biltong.

## Header 2

> This is a blockquote following a header. Bacon ipsum dolor sit amet t-bone doner shank drumstick, pork belly porchetta chuck sausage brisket ham hock rump pig. Chuck kielbasa leberkas, pork bresaola ham hock filet mignon cow shoulder short ribs biltong.

### Header 3

```
This is a code block following a header.
```

#### Header 4

- This is an unordered list following a header.
- This is an unordered list following a header.
- This is an unordered list following a header.

##### Header 5

1. This is an ordered list following a header.
2. This is an ordered list following a header.
3. This is an ordered list following a header.

###### Header 6

| What    | Follows  |
| ------- | -------- |
| A table | A header |
| A table | A header |
| A table | A header |

---

There's a horizontal rule above and below this.

---

Here is an unordered list:

- Salt-n-Pepa
- Bel Biv DeVoe
- Kid 'N Play

And an ordered list:

1. Michael Jackson
2. Michael Bolton
3. Michael Bublé

And an unordered task list:

- [x] Create a sample markdown document
- [x] Add task lists to it
- [ ] Take a vacation

And a "mixed" task list:

- [ ] Steal underpants
- ?
- [ ] Profit!

And a nested list:

- Jackson 5
  - Michael
  - Tito
  - Jackie
  - Marlon
  - Jermaine
- TMNT
  - Leonardo
  - Michelangelo
  - Donatello
  - Raphael

Definition lists can be used with HTML syntax. Definition terms are bold and italic.

<dl>
    <dt>Name</dt>
    <dd>Godzilla</dd>
    <dt>Born</dt>
    <dd>1952</dd>
    <dt>Birthplace</dt>
    <dd>Japan</dd>
    <dt>Color</dt>
    <dd>Green</dd>
</dl>

---

Tables should have bold headings and alternating shaded rows.

| Artist          | Album          | Year |
| --------------- | -------------- | ---- |
| Michael Jackson | Thriller       | 1982 |
| Prince          | Purple Rain    | 1984 |
| Beastie Boys    | License to Ill | 1986 |

If a table is too wide, it should condense down and/or scroll horizontally.

<!-- prettier-ignore-start -->

| Artist            | Album           | Year | Label       | Awards   | Songs     |
|-------------------|-----------------|------|-------------|----------|-----------|
| Michael Jackson   | Thriller        | 1982 | Epic Records | Grammy Award for Album of the Year, American Music Award for Favorite Pop/Rock Album, American Music Award for Favorite Soul/R&B Album, Brit Award for Best Selling Album, Grammy Award for Best Engineered Album, Non-Classical | Wanna Be Startin' Somethin', Baby Be Mine, The Girl Is Mine, Thriller, Beat It, Billie Jean, Human Nature, P.Y.T. (Pretty Young Thing), The Lady in My Life |
| Prince            | Purple Rain     | 1984 | Warner Brothers Records | Grammy Award for Best Score Soundtrack for Visual Media, American Music Award for Favorite Pop/Rock Album, American Music Award for Favorite Soul/R&B Album, Brit Award for Best Soundtrack/Cast Recording, Grammy Award for Best Rock Performance by a Duo or Group with Vocal | Let's Go Crazy, Take Me With U, The Beautiful Ones, Computer Blue, Darling Nikki, When Doves Cry, I Would Die 4 U, Baby I'm a Star, Purple Rain |
| Beastie Boys      | License to Ill  | 1986 | Mercury Records | noawardsbutthistablecelliswide | Rhymin & Stealin, The New Style, She's Crafty, Posse in Effect, Slow Ride, Girls, (You Gotta) Fight for Your Right, No Sleep Till Brooklyn, Paul Revere, Hold It Now, Hit It, Brass Monkey, Slow and Low, Time to Get Ill |

<!-- prettier-ignore-end -->

---

Code snippets like `var foo = "bar";` can be shown inline.

Also, `this should vertically align` ~~`with this`~~ ~~and this~~.

Code can also be shown in a block element.

```
var foo = "bar";
```

Code can also use syntax highlighting.

```javascript
var foo = "bar";
```

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```javascript
var foo =
  "The same thing is true for code with syntax highlighting. A single line of code should horizontally scroll if it is really long.";
```

Inline code inside table cells should still be distinguishable.

| Language   | Code               |
| ---------- | ------------------ |
| Javascript | `var foo = "bar";` |
| Ruby       | `foo = "bar"`      |

---

Small images should be shown at their actual size.

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

Large images should always scale down and fit in the content container.

![Branching](https://guides.github.com/activities/hello-world/branching.png)

```
This is the final element on the page and there should be no margin below this.
```
