---
sort: 5
---

# How regression is used to find answers for questions

Assume that we are researching question how the age of the person affects his wages.
To answer this question first we need data that have variation in the ages of people, and we want to sat that with the change of age, does that make difference in wages.

$$ wages = ages + error\_term $$

```tip
Basically every empirical paper needs to have three things.
- Outcome variable (Left-hand-side).
- Independent variable (Right-hand-side, explanatory variable)
- Variation in the independent variable. (Variation in the independent variable should be "good", unrelated to changes in outcome variable)
```


## Hit or Miss? The Effect of Assassinations on Institutions and War.
[Link to the paper](https://economics.mit.edu/files/3055)

Idea is we are not going to look at all leadership changes, but we look at very small set of changes, where assassin tried to take a shot at the president. We will treat as "good"(quasi-random) variation as if it was a randomized experiment. However decision to assasinate president is for sure not random. What random here is the outcome of assasination, whether attack was sucessfull or not.
For example, idea that want to compare Reagan assasination and Kennedy assasination, or in other words whether the bullet actually successfully killed the president or not is close to random as possible.

To see whether changing the leader matters, we look at assassination attempt $$i$$ and estimate the following regression:
$$ y_i = \beta SUCCESS_i + \epsilon_i $$

- $$y_i$$ is:the outcome variable (e.g., change in democracy levels from year before assassination attempt to 5 years after attempt)
- $$SUCCESS_i$$ is: a dummy variable: = 1 if leader killed and = 0 if survives
- $$\epsilon_i$$ is: an error term (Noise)
- $$\beta$$ is: the average impact of a successful assassination on y

![table2](/assets/images/hit_or_miss_table2.png)

```note
You can have in mind, picture where 
y is just one column in your spreadsheet, that is your outcome variable. X's is the columns that is your data. $$\epsilon$$ is the missing data in your spreadsheet, that describes real formula in the world for the phenomena that you researching by.