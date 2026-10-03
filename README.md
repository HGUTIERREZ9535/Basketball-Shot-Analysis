# OKC Thunder Shot Analysis 🏀

## 1. Introduction

### What question are we trying to answer?

The goal of this analysis is to explore which factors are associated with shot-making success and identify variables that could be useful for a future model predicting the probability of a shot being made.

### Why does shot selection matter?

Shot selection matters because some types of shots have higher make percentages than others. Understanding these differences can help identify factors that may be useful when predicting how successful a shot could be.

---

# 2. Dataset

The dataset contains **425,719 shots**.

### Variables Used

**Individual variables:**

* Shot Distance
* Shot Type
* Contested
* Number of Contesters
* Closest Defender Distance
* Game State
* Shot Clock
* Dribbles Before Shot
* Three-Point Shot

**Cross-analysis:**

* Distance × Contested
* Distance × Shot Type
* Shot Clock × Contested
* Shot Clock × Three-Point Shot
* Dribbles × Shot Distance
* Dribbles × Three-Point Shot
* Number of Contesters × Three-Point Shot
* Game State × Shot Type

**Outcome variable:** `Outcome` — whether the shot was made (`True`) or missed (`False`).

---

# 3. Methodology

### Grouping

The data was grouped into meaningful categories, such as shot-distance ranges, shot-clock ranges, number of contesters, and shot types. This allowed make percentages to be compared across different conditions.

### Make Percentage

Make percentage was calculated by taking the average of the `Outcome` variable for each group and multiplying it by 100. This provided the percentage of shots that were made within each category.

### Cross-Analysis

Multiple variables were analyzed together to identify whether patterns changed when considering more than one factor. Examples include **Distance × Contested**, **Shot Clock × Contested**, **Distance × Shot Type**, and **Dribbles × Shot Distance**.

### Sample-Size Consideration

The number of shot attempts in each category was reviewed before interpreting the results. Categories with very small sample sizes were treated cautiously because they could produce percentages that do not reliably represent a broader pattern.

---

# 4. Findings

## Shot Distance

Based on this analysis, shorter shot distances tend to have higher make percentages. Shots taken within **0–5 ft** had a **63.55%** make percentage, compared with only **21.20%** for shots from **30+ ft**.

![Shot Distance](https://github.com/HGUTIERREZ9535/OKC-Thunder-Shot-Analysis/blob/9b987505f065fca2aef5e3b03c3680e847247cc0/shot_distance.png)

---

## Shot Type

Shot type appears to be associated with make percentage. Dunks had one of the highest make percentages at **88.53%**, while heaves had the lowest at **9.48%**.

This represents a large difference in make percentage between the two shot types, suggesting that shot type is an important factor associated with shooting success.

![Shot Type](visualizations/shot_type.png)

---

## Shot Clock

There is a clear association between shot-clock time and make percentage. Shots with **0–5 seconds** remaining had a **38.18%** make percentage, compared with **59.04%** for shots with **20+ seconds** remaining.

Overall, having more time on the shot clock is associated with a higher make percentage.

![Shot Clock](visualizations/shotclock.png)

---

## Distance × Contested

There is a clear pattern between shot distance, contest status, and make percentage. As shot distance increases, make percentage generally decreases. In addition, non-contested shots have a higher make percentage than contested shots across the distance categories.

This suggests that both shot distance and contest status are associated with shooting success.

![Distance and Contested](visualizations/distance_contested.png)

---

## Contested vs. Non-Contested Shots

Non-contested shots had a **62.09%** make percentage, compared with **43.83%** for contested shots.

Both groups had large sample sizes, making this one of the clearer patterns in the analysis.

![Contested vs Non-Contested](visualizations/contested.png)

---

## Shot Clock × Contested

There is a clear association between shot-clock time and make percentage. Make percentage generally increases as the amount of time remaining on the shot clock increases.

In addition, non-contested shots consistently have higher make percentages than contested shots across the shot-clock categories.

![Shot Clock and Contested](visualizations/shotclock_contested.png)

---

## Distance × Shot Type

Shot distance and shot type were analyzed together to determine whether the relationship between distance and make percentage changes depending on the type of shot.

The grouped bar chart allows the make percentage of different shot types to be compared across shot-distance categories.

![Shot Type and Distance](visualizations/shottype_distance.png)

---

## Other Analyses

Additional relationships were explored, including:

* Shot Clock × Three-Point Shot
* Dribbles × Shot Distance
* Dribbles × Three-Point Shot
* Number of Contesters × Three-Point Shot
* Game State × Shot Type

These analyses were used to determine whether combining variables provided additional patterns that were not visible when analyzing individual variables.

---

# 5. Limitations

### Small Categories

Some combinations of variables contained very few shot attempts. These groups can produce unusually high or low make percentages that may not represent a reliable overall pattern.

### Uneven Sample Sizes

Some groups contained hundreds of thousands of shot attempts, while others contained only a small number of observations. This difference in sample size should be considered when comparing categories.

### Association Does Not Equal Causation

The analysis identifies associations between variables and make percentage, but it does not prove that a specific factor directly causes a shot to be made or missed.

### Variables Without Clear Patterns

Some analyses did not show consistent patterns or had sample-size limitations. These variables were not used as primary findings because the results were not strong enough to support a clear conclusion.

---

# 6. Conclusion

### What did the analysis reveal?

The analysis identified several factors associated with shooting success. It also showed the importance of considering sample size when interpreting results.

One of the most important statistical concepts from this analysis is that **association does not mean causation**. The results can show that variables are related to make percentage, but they cannot establish that those variables directly cause a shot to be made or missed.

### What factors were most consistently associated with shooting success?

The analysis identified several factors consistently associated with shooting success. **Shot distance, shot type, contest status, and shot-clock time** showed some of the clearest patterns.

For example, shots from **0–5 ft** had a **63.55%** make percentage, while shots from **30+ ft** had a **21.20%** make percentage.

Similarly, shots with **20+ seconds** remaining on the shot clock had a **59.04%** make percentage, compared with **38.18%** for shots with **0–5 seconds** remaining.

Dunks also had a substantially higher make percentage at **88.53%**, compared with **9.48%** for heaves.

### What could be analyzed next?

For future analysis, additional variables such as **player age, shooter identity, defender identity, player position, game situation, and location on the court** could be explored.

These variables could help determine whether additional information improves a future model designed to predict the probability of a shot being made.
