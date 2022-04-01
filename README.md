# Which Debts Are Worth the Bank's Effort

After a debt has been legally declared "uncollectable" by a bank, the account is considered "charged-off." But that doesn't mean the bank walks away from the debt.
They still want to collect some of the money they are owed. Scoring the account to assess the expected recovery amount, that is the expected amount that the bank may be able to receive from the customer in the future.

This amount is a function of the probability of the customer paying the total debt and other factors that impact the ability and willingness to pay.

The bank has implemented different recovery strategies at different thresholds ($1000, $2000, etc.) where the greater the expected recovery amount, the more effort the bank puts into contacting the customer. 

For low recovery amounts (Level 0), the bank just adds the customer's contact information to their automatic dialer and emailing system. For higher recovery strategies, the bank incurs more costs as they leverage human resources in more efforts to obtain payments. 

Each additional level of recovery strategy requires an additional $50 per customer so that customers in the Recovery Strategy Level 1 cost the company $50 more than those in Level 0. Customers in Level 2 cost $50 more than those in Level 1, etc.

The big question: does the extra amount that is recovered at the higher strategy level exceed the extra $50 in costs? In other words, was there a jump (also called a "discontinuity") of more than $50 in the amount recovered at the higher strategy level? 

#Summary of the Levels and thresholds :

Level 0: Expected recovery amounts >$0 and <=$1000
Level 1: Expected recovery amounts >$1000 and <=$2000
The threshold of $1000 separates Level 0 from Level 1

other factors besides Expected Recovery Amount that also varied systematically across the $1000 threshold

does the customer age or sex show a jump (discontinuity) at the $recovery amount ?

we will test age them against the recovery amount then we will run explotory graphical analysis for the recoverd amount and analyse it statically 

then we will take a regression-based approach to estimate the program impact at the $1000 threshold using data that is just above and below the threshold.

by building two models. The first model doesn’t not have a threshold while the second will include a threshold.
the first model predicts the actual recovery amount (dependent variable) as a function of the expected recovery amount (independent variable)
Examining the adjusted R-squared to see the percent of variance explained by the model. In this model, we are not representing the threshold but simply seeing how the variable used for assigning the customers (expected recovery amount) relates to the outcome variable (actual recovery amount).
by seeing that the expected recovery amount's regression coefficient is statistically significant.

The second model adds an indicator of the true threshold to the model (in this case at $1000).

We will create an indicator variable (either a 0 or a 1) that represents whether or not the expected recovery amount was greater than $1000. When we add the true threshold to the model, the regression coefficient for the true threshold represents the additional amount recovered due to the higher recovery strategy. That is to say, the regression coefficient for the true threshold measures the size of the discontinuity for customers just above and just below the threshold.

If the higher recovery strategy helped recovery more money, then the regression coefficient of the true threshold will be greater than 0. If the higher recovery strategy did not help recovery more money, then the regression coefficient will not be statistically significant.


The regression coefficient for the true threshold was statistically significant with an estimated impact of around $278. This is much larger than the $50 per customer needed to run this higher recovery strategy.

Before ending the notebook we tested it again to see if this results wasn't due to choosing an expected recovery amount window of $900 to $1100. Let's repeat this analysis for the window from $950 to $1050 to see if we get similar results.

and the results  was Whether we used a wide ($900 to $1100) or narrower window ($950 to $1050), the incremental recovery amount at the higher recovery strategy is much greater than the $50 per customer it costs for the higher recovery strategy. So we conclude that the higher recovery strategy is worth the extra cost of $50 per customer.


