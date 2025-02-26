# Trust-Based-Recommendation-Model
The function calculates user-user similarity using:
1.	Pearson Correlation Coefficient (PCC)
Measures the strength of linear relationships between users.
2.	Distance Matrix 
Measure the distance between user ratings
PCC : Gives strength of correlation. <br>
Distance : Gives the magnitude difference.
Why do we need these functions?
•	Because, if 2 users have similar ratings, we can use one rating to predict the missing ratings of another user.
•	PCC – Measures correlation but ignores magnitude.
•	Distance Matrix – Provides magnitude-based comparisons but do not consider directions of preference.
This way, these both help balances both aspects.
