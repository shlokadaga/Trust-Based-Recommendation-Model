# Trust-Based-Recommendation-Model

## Calculating Similarity
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


## Calculating Confidence
It computes how similar the opinion of two users is based on user-item interaction, similarity, and confidence in those similarities. <br>
Thus, based on identical opinions, we can determine the similarity or closeness between users. Basically, for a pair of users, an identical opinion score is generated. <br>

In order to determine whether the opinion of 2 users is identical or not, we set an epsilon value which is a small value used to determine whether 2 numbers are close enough to be considered equal. And in the context of our project, “epsilon”, is the threshold for similarity, which means that if the value differs by less than epsilon, than it is treated as “equal” i.e. “identical”. <br>
Without, the model would have treat two user as completely different, just because they gave a rating of 4.5 and other gave 4.6
