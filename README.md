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

## Calculate Incipient Trust
It calculates incipient trust between 2 users based on 3 factors – Similarity, Confidence, Identical Opinion.<br>

There are 3 concepts here:<br>
1.	Direct Trust – This is a trust which is direct between 2 user which is calculated using similarity, confidence and identical opinion. A -> B. <br>
2.	Indirect Trust – This is the kind of trust that propagates between user i.e. It User A Trusts User B and User B trusts User C, then User A trusts User C. <br>
3.	Incipient Trust – The final trust value generated by combining direct and propagated trust. <br>

Suppose there are 3 matrices for similarity, confidence, identical opinions which includes the relationship between 2 users.<br>
And each of the users has a threshold value for similarity, confidence, and identical opinions.<br>
Similarity Threshold : [0.5, 0.6, 0.3, 0.5]<br>
Confidence Threshold : [ 0.5, 0.6, 0.3, 0.4]<br>
Identical Opinion Threshold : [0.4, 0.5, 0.2, 0.3]<br>

In order to calculate Direct Trust, we check different conditions: <br>
1.	If similarity score is higher than sval of an user(similarity_val >= sval), also If confidence score is higher than c_val of an user, If opinion score is higher than o_val of an user:<br>
= (3 x similarity_val x confidence_val x opinion_val) / (similarity_val + confidence_val + opinion_val)<br>
Else If opinion score is not higher than opinion_val<br>
=  (2 x similarity_val x confidence_val ) / (similarity_val + confidence_val )<br>
2.	If every score (similarity, identical opinion) is high, but confidence score is less than c_val<br>
= (2 x similarity_val x opinion_val) / (similarity_val + opinion_val)<br>
3.	If everything is high(confidence, opinion), but the similarity score is not high than s_val<br>
= (2 x confidence_val x opinion_val) / (confidence_val + opinion_val)<br><br>
Propagate Trust<br>
If User A Trusts User B and User B trusts User C, then User A trusts User C. Here some trust is transferred from A to C.<br>
