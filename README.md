# Trust-Based-Recommendation-Model
The function calculates user-user similarity using:
1.	Pearson Correlation Coefficient (PCC)
Measures the strength of linear relationships between users.<br>
2.	Distance Matrix 
Measure the distance between user ratings
PCC : Gives strength of correlation. <br>
Distance : Gives the magnitude difference.<br>
Why do we need these functions? <br>
Because, if 2 users have similar ratings, we can use one rating to predict the missing ratings of another user. <br>
•	PCC – Measures correlation but ignores magnitude. <br>
•	Distance Matrix – Provides magnitude-based comparisons but do not consider directions of preference. <br>
This way, these both help balances both aspects. <br>
