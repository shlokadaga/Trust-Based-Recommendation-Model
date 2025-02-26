# Trust-Based-Recommendation-Model
The function calculates user-user similarity using:
1.	Pearson Correlation Coefficient (PCC)
Measures the strength of linear relationships between users.
2.	Distance Matrix 
Measure the distance between user ratings
PCC : Gives strength of correlation.
Distance : Gives the magnitude difference.
Why do we need these functions?
•	Because, if 2 users have similar ratings, we can use one rating to predict the missing ratings of another user.
•	PCC – Measures correlation but ignores magnitude.
•	Distance Matrix – Provides magnitude-based comparisons but do not consider directions of preference.
This way, these both help balances both aspects.

Example: 
User’s rating for Movies (0 means user has not given any rating)
	M1	M2	M3	M4
User 1	5	3	0	0
User 2	4	0	0	2
User 3	0	3	4	0
User 4	2	0	4	5

Average Rating of User 1 = (5 + 3) / 2 = 4
Average Rating of User 2 = (4 + 2) / 2 = 3

Common Rated movie between User 1, User 2 – Item 01
