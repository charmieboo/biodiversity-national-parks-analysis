
![Your paragraph text](https://github.com/user-attachments/assets/493b6e41-4425-4303-9510-6dd0d3fa0ae5)

# Project Overview
=================================================================================================================================
For this project, I will interpret data from the National Parks Service about endangered species in different parks. I will perform some data analysis on the conservation statuses of these species and investigate if there are any patterns or themes to the types of species that become endangered. This project scopes, cleans, analyzes, visualizes, and interprets biodiversity data, answering questions such as:
  * What is the distribution of conservation status for animals?
  * Are certain types of species more likely to be endangered?
  * Are the differences between species and their conservation status significant?
  * Which species were spotted the most at each park?

# Data
=================================================================================================================================
The data for this project was sourced from [Codecademy](https://www.codecademy.com) and includes two datasets:
* Species Info: Information on species observed in National Parks.
* Observations: Sightings of species in different parks over the past 7 days.

### Data Loading
The two datasets were loaded using Python's pandas library for manipulation, with visualization performed using matplotlib and seaborn:
```
import pandas as pd
import numpy as np
from matplotlib import pyplot as plt
import seaborn as sns

species = pd.read_csv('species_info.csv', encoding='utf-8')
observations = pd.read_csv('observations.csv', encoding='utf-8')
```

### Data Analysis
=================================================================================================================================
#### Distribution of Conservation Status
The majority of species (5,633) were categorized as "No Intervention," meaning no conservation measures were required. A small number were endangered or in recovery.

#### Protected Species by Category
Analyzing the distribution of protected species across different categories showed that mammals and birds had the highest number of protected species.

#### Statistical Significance 
Chi-squared tests were performed to test the significance of differences in protection rates between species. A test between mammals and reptiles returned a p-value of 0.039, indicating a statistically significant difference in protection status between these groups.
```
from scipy.stats import chi2_contingency
contingency2 = [[30, 146], [5, 73]]
chi2_contingency(contingency2)
```

#### Prevalent Species
The most common animal across all parks was the bat, with 23 occurrences. Bats were predominantly found in Yellowstone National Park.

# Findings
* What is the distribution of conservation status for species?
    - The vast majority of species were not part of conservation.(5,633 vs 191)
* Are certain types of species more likely to be endangered?
    - Mammals and Birds had the highest percentage of being in protection: 17% and 15.4% respectively.
![Species according to conservation status](https://github.com/user-attachments/assets/bddc4519-8997-4482-93f2-d451b4bb5916)
* Are the differences between species and their conservation status significant?
    - While Mammals and Birds did not have significant difference in conservation percentage, mammals and reptiles exhibited a statistically significant difference.
* Which animal is most prevalent and what is their distribution amongst parks?
    - The study found that bats occurred the most number of times and they were most likely to be found in Yellowstone National Park.
![Observation of bats per week](https://github.com/user-attachments/assets/9f51e04d-8b5c-4bae-ad09-2c8114bf16df)


# Further Research
Future work could expand on this analysis by:
* Incorporating data over time to observe trends in species populations.
* Considering the area of each park to normalize observations by park size.
* Analyzing the spatial distribution of species to understand if sightings are geographically clustered.
