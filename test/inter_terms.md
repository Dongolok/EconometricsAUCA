---
sort: 8
---

# Interaction terms

You can introduce dummy variable is not just intercept shifter, but as interacted with X variables. 

For example,
We have program that are randomly assigned to participant. We have female and male participants. 
You might be interested in knowing whether treatment affects men differently than women. To do that you need to run regression with _interaction terms_. Esentially interaction terms, are just multiplication of two dummy variables.

$$ Y_i = \alpha + \beta D_i + \gamma M_i + \delta M_i*D_i + \epsilon_i  (1)$$

Let assume that D is the dummy variable 1 if the patient recived vaccination shot, 0 if not. Y is the probability of the person catching coronovirus after one month. M is the gender dummy variable 1 if person is male, and 0 if the person is female.

|Gender| Vaccination  | Formula |
| ----| ------| ---------| 
|Male | Not vaccinated |$$ \alpha + \gamma $$ |
|Male | Vaccinated | $$ \alpha + \beta + \gamma + \delta $$|
|Female| Not vaccinated | $$\alpha $$ |
|Female | Vaccinated |  $$ \alpha + \beta$$ |

| Coefficient | Interpretation |
| ---- | ------------|
| $$\alpha$$ | 