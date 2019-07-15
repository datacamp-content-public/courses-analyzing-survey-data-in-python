---
title: 'Chapter Title Here'
description: 'Chapter description goes here.'
free_preview: true
---

## Example coding exercise

```yaml
type: NormalExercise
key: e8c1edbe67
lang: python
xp: 100
skills: 2
```

This is an example exercise.

`@instructions`


`@hint`


`@pre_exercise_code`
```{python}

```

`@sample_code`
```{python}

```

`@solution`
```{python}

```

`@sct`
```{python}

```

---

## Graphing continuous data

```yaml
type: VideoExercise
key: 787a96637c
xp: 50
```

`@projector_key`
4b324f55577ad2685db07ab5a50c9358

---

## Chi2_Capstone_draft

```yaml
type: TabExercise
key: d757db2a97
xp: 100
```

Performing a chi-square hypothesis test measures the relationship between a categorical input and categorical output. In this exercise we will to a chi-square test of association, to see if there is a relationship between being left (or right) handed and being male (or female).

The Null hypothesis H_0: males and females are equally likely to be left (or right) handed, P_male = P_female (probability of a lefty being male equals probability of being female)
Alternative hypothesis H_A: There is an association  between gender and handedness (P_male != P_female for someone left handed)

`@pre_exercise_code`
```{python}

```

***

```yaml
type: NormalExercise
key: db15395ed0
xp: 50
```

`@instructions`
A hypothesis done in code consists of two parts; the math part and the code part.

The math part consists of stating the hypothesis, our degrees of freedom, critical value of the test statistic (based on degrees of freedom), the desired p_value threshold

The code part consists of:
	* isolating the data we want from the data frame
    * setting up a table to count the values of each category (2x2 for this case)
    * putting the data into the appropriate python functions to get the test statistic, degrees of freedom and p-values
    * comparing the test statistic and p-value in an if-then statement that will reject or accept the null hypothesis

`@hint`


`@sample_code`
```{python}

```

`@solution`
```{python}

```

`@sct`
```{python}

```

***

```yaml
type: NormalExercise
key: 605fed9295
```

`@instructions`
We first must import the relevant functions/packages we need to perform the hypothesis test. These are;
* numpy
* chi2_contingency and chi2 from the stats package of scipy

`@hint`


`@sample_code`
```{python}

```

`@solution`
```{python}
import numpy as np
from scipy.stats import chi2_contingency,chi2
```

`@sct`
```{python}

```

***

```yaml
type: NormalExercise
key: 8823c63a8f
xp: 50
```

`@instructions`
Out of our dataframe we need value counts of the handed-ness for both males and females.
Thus, create a dataframe for the lefties and one for the righties that performs value counts on the gender

`@hint`
right = df[df['Left - right handed']==______][_____].______
left = df[df['Left - right handed']==______][______].______

`@sample_code`
```{python}

```

`@solution`
```{python}
right = df[df['Left - right handed']=='right handed']['Gender'].value_counts()
left = df[df['Left - right handed']=='left handed']['Gender'].value_counts()
```

`@sct`
```{python}

```

***

```yaml
type: NormalExercise
key: eff3873b19
```

`@instructions`
Next, using the values we just put into our left and right dataframes, we must put these values into a single table (numpy array). Call this table observations

`@hint`


`@sample_code`
```{python}
observations = np.array([_____,_____])
```

`@solution`
```{python}
observations = np.array([right,left])
```

`@sct`
```{python}

```

***

```yaml
type: NormalExercise
key: a42a62753c
```

`@instructions`
The chi2_contingency function outputs the chi2_stat, p_value, dof (degrees of freedom) and expected_values (IN THAT ORDER).

Using this function on our observations array we just made, extract those values.

`@hint`


`@sample_code`
```{python}
_____,_____,_____,_____ = chi2_contingency(_________)
```

`@solution`
```{python}
chi_square_stat, p_value, dof, expected = chi2_contingency(observations)
```

`@sct`
```{python}

```

***

```yaml
type: NormalExercise
key: 0904734431
```

`@instructions`
To finish the test we must determine our chi2_critical value. This is done using the .ppf() method of the chi2 function we imported.

The arguments of the function are:
* 1-alpha (alpha is our threshold probability)
* degrees of freedom.

`@hint`


`@sample_code`
```{python}
alpha = 0.05
Chi2_critical = chi2.ppf(_____,_____)
```

`@solution`
```{python}
alpha = 0.05
Chi2_critical = chi2.ppf(1-alpha,dof)
```

`@sct`
```{python}

```

***

```yaml
type: NormalExercise
key: cec58955aa
```

`@instructions`
Finally, we should reject the null hypothesis if our p_value is less than our alpha, and our test statistic is greater than our threshold statistic. Create an if-then code the prints "reject null hypothesis" if the criteria is met, elsefail

`@hint`
The criteria is;
if (Chi2_critical<chi_square_stat) and (p_value<alpha) (then reject null hypothesis)

other wise
fail to reject null hypothesis

`@sample_code`
```{python}

```

`@solution`
```{python}
if (Chi2_critical<chi_square_stat) and (p_value<alpha):
    print("Reject Null")
else:
    print("Fail to reject null hypothesis")
```

`@sct`
```{python}

```
