# MechaCar_Statistical_Analysis

## Overview of Project

### Purpose
The purpose of this analysis is to use R to perform statistical analysis on a dataset of car information provided by AutosRUs, and produce the following deliverables:

1. A multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes 

2. A set of summary statistics for the company's suspension coils, both as a whole and by individual lot

3. A set of t-tests to determine if the manufacturing lots are statistically different from the mean population, both grouped together as a total and by individual lot

4. a design for a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers

## Results
### Linear Regression to Predict MPG
![Linear Regression](https://github.com/Nveatch/MechaCar_Statistical_Analysis/blob/main/Resources/del_1.png)

**Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?**
From the table, the intercept, vehicle length, and ground clearance are unlikely to cause random variance (and thus provide non-random variance) due to their p-values of 5.08e-08, 2.60e-12, and 5.21e-08 respectively.

**Is the slope of the linear model considered to be zero? Why or why not?**
No, the slope of the linear model is not considered to be zero, due to the p value of 5.35e-11. this is below the significance level of 0.05, and thus rejects the null hypothesis of the slope being zero.

**Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?**
Yes, as the r-squared value is 0.7149, indicating a decent fit to the data, and the p-value is significant, indicating a non-zero slope and thus a correlation.

### Summary Statistics on Suspension Coils
**The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?**
![Total Summary](https://github.com/Nveatch/MechaCar_Statistical_Analysis/blob/main/Resources/del_2_total_summary.png)

As shown in the above dataframe, the variance for all lots in total is 62.29356, and thus does meet the design specification of not exceed a variance of 100 pounds per square inch.

![Lot Summary](https://github.com/Nveatch/MechaCar_Statistical_Analysis/blob/main/Resources/del_2_lot_summary.png)

However, as shown in this individual lot summary, lot 3 by itself has a variance of 170.2861224, which does not meet the specification. Lots 1 and 2 do meet the specification though (variances of 0.9795918 and 7.4693878 respectively). 

### T-Tests on Suspension Coils
Our goal with these t-tests is to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 pounds per square inch.

**Total of all Lots**
![Lot Summary](https://github.com/Nveatch/MechaCar_Statistical_Analysis/blob/main/Resources/del_3_all_lots.png)

The P-value is 0.06028, outside out significance level of 0.05, so we fail to reject the null hypothesis (there could or could not be a statistical difference)

**Each Lot Separately**
![Lot Summary](https://github.com/Nveatch/MechaCar_Statistical_Analysis/blob/main/Resources/del_3_each_lot.png)

* Lot 1 (in red) has a p-value of 1, outside out significance level of 0.05, so we fail to reject the null hypothesis (there could or could not be a statistical difference)

* Lot 2 (in yellow) has a p-value of 0.6072, outside out significance level of 0.05, so we fail to reject the null hypothesis (there could or could not be a statistical difference)

* Lot 3 (in blue) has a p-value of 0.04168, within our significance level of 0.05, so we reject the null hypothesis (there is a statistical difference between this sample and the population mean of 1500 PSI)

### Study Design: MechaCar vs Competition
A statistical study I would use to compare MechaCar vehicles against other manufactureers would be based on their safety rating, based on the numerical value between 0 and 5 given by the NHTSA. To do this, the data I would need would be the average safety rating for each manufacturer's line of cars, and what's considered a good safety rating of all cars from the NHTSA (4 or 5). I would then compare each manufacturer's mean safety rating with the NHTSA's good number using a 1-sample t-test, in order to see if there was a statistical difference between each manufacturer's average safety rating, and the "population" (NHTSA's good rating). In this study, my null hypothesis would be that there is no statistical difference between the manufacturer's score and the NHTSA's, and my alternative hypothesis would be that there is a statistical difference between the two. If MechaCar's data failed to reject the null hypothesis, it could indicate that the safety of its cars is statistically similar to the NHTSA's good rating.   



