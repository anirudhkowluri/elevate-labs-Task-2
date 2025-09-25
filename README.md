This project is ablout EDA and their summaries 
1) Summary statistics:
   
Here are the summary statistics (count, mean, std, min, quartiles, max, plus median) for numeric features:
Brief note:

Survived rate is about 38%.
Sex_male mean near 0.65 indicates roughly two-thirds of passengers are male.
Scaled features (Age_scaled, SibSp_scaled, Parch_scaled, Fare_scaled) have mean around 0 and std near 1 as expected from standardization.
I computed the summary statistics with median added.

2) Distributions: Histograms and Boxplots summary:
   Quick takeaways:
Survived is binary and imbalanced toward 0 (non-survivors).
Pclass skews toward 3rd class.
Sex_male shows more males than females.
Fare_scaled has a long right tail (a few very high fares).
SibSp_scaled and Parch_scaled show strong mass at the lower end (most had few or no siblings/spouses or parents/children aboard).
Age_scaled is roughly normal with mild skew and some tails.

3)Feature relationships: Correlation and Pairplot summary
Notable correlations:

Survived and Sex_male: negative association, suggesting females tended to survive more.
Survived and Pclass: negative correlation; higher class (lower number) is associated with better survival.
Survived and Fare_scaled: positive correlation; higher fares associated with better survival (consistent with class effect).
Pclass and Fare_scaled: strong negative correlation; third-class fares were lowest.
Age_scaled has weak correlation with Survived, consistent with the common finding that age alone is a weaker predictor versus sex/class.

4) Patterns, Trends, and Anomalies
Patterns and trends:

Class and survival: Passengers in higher classes (1st class) tend to survive at higher rates. This is visible in the negative correlation between Survived and Pclass and the positive correlation between Survived and Fare_scaled.
Sex and survival: Strong negative correlation between Survived and Sex_male suggests the well-known women-and-children-first effect.
Fare distribution: Right-skewed with a few extreme high values—indicative of luxury tickets and cabins.
Family structure: SibSp_scaled and Parch_scaled are heavily concentrated at the minimum values, meaning most passengers traveled alone or with very few relatives.
Anomalies:

Fare outliers: Clear high-end outliers in Fare_scaled (boxplots). These may disproportionately influence models and should be handled or capped if modeling.
Family counts: A small number of extreme scaled values suggest a handful of passengers with unusually large family groups onboard.

5) Feature-level Inferences from Visuals
Sex_male is a strong predictor: The visual distributions and correlations indicate females had higher survival odds than males.
Socioeconomic proxy (Pclass, Fare): Higher fares and lower Pclass numbers align with higher survival—indicating access advantages (cabins near lifeboats, deck access, crew assistance).
Embarked effects are minor here: Embarked_Q and Embarked_S show weak relationships with survival; any port-of-embarkation effect appears subtle relative to sex/class.
Age on its own is weak: The low absolute correlation with Survived suggests age by itself is not dominant, although interactions (e.g., with sex or class) may matter.
Family counts may have non-linear effects: While average effects are weak in correlations, pairplots show mass at zero with a long tail; survival may vary for small families vs. large groups or solo travelers—worth exploring with binned or interaction features.

