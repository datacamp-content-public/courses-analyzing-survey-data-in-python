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
Alternative hypothesis H_A: There is an association  between gender and handedness (P_male != P_female)

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
	* isolating the data we want from the dataframe
    * setting up a table to count the values of each category (2x2 for this case)
    * putting it into

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
key: 908ff1ec58
xp: 50
```

`@instructions`


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
