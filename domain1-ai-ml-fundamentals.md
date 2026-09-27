Day 1
#today learned supervised learning & unsupervised learning
Supervised is - label data (Answer key)
ex- if we have answer key along with the question then we can easily find solve the questions.

Unsupervised is no label data (No Answer key)
ex- In Railway station many peoples are travelling on daily basis. if we get to know the travellers details basis of ages then we need to segregate travellers on their age groups.

#Reinforcement learning- An agent takes actions in an enviroment and after each action he gets reward or penalty. It has no answer key and no body tell the right move directly. it learns purely through error and trial.

Ex- i recommendates to HR one employee if my recommnedation is good than ill get reward(refferal ) else ill get penalaty(bad mark from HR). for this trial next time ill recommneds good refferal

#Over fitting and underfitting
Overfitting-Model learned too much (memorised)-> great on training data but bad on new data


Underfitting- Model didn't learn enough-> bad on training and new data

overfitting = "high accuracy on training data, low accuracy on test/unseen data."

#Bias-variance tradeoff

Bias = too simple, misses the pattern. Variance = too sensitive, memorizes noise. You're always trading one against the other — you can't kill both.

High bias = all your darts land in the same wrong spot, far from the bullseye (consistently wrong)
High variance = your darts scatter all over the board, sometimes near the bullseye, sometimes way off (inconsistent)
Ideal = darts clustered tightly around the bullseye

Day 2
IDP- intelligent Document Processing
NLP-Natural Language Processing


________________________________________________________________
# Domain 1: AI/ML Fundamentals

## Supervised Learning
Trained on labeled data (has an answer key) — model learns the mapping between input and known output.
Example: Email spam filter trained on emails already tagged "spam"/"not spam."

## Unsupervised Learning
No labels at all — no answer key exists anywhere. Model finds hidden structure/patterns/groupings on its own.
Example: Grouping metro travelers into clusters based on age, with no pre-existing categories given.

## Reinforcement Learning
An agent takes actions in an environment, gets a reward or penalty after each action (no answer key, no one tells it the right move directly). Learns through trial and error to maximize total reward over time.
Example: Recommending job candidates — good recommendation = referral reward, bad one = penalty from HR. Over time, judgment improves based on this feedback loop.

## Overfitting vs Underfitting
- **Underfitting:** model too simple, misses the real pattern → poor performance on BOTH training and new data.
- **Overfitting:** model learns training data too precisely (memorizes noise) → great on training data, poor on new/unseen data.

## Bias-Variance Tradeoff
- **Bias:** model too simple → consistently wrong in the same way (underfitting).
- **Variance:** model too complex/sensitive → inconsistent, changes wildly with small data changes (overfitting).
- **Tradeoff:** reducing one tends to increase the other. Can't minimize both — aim for the middle ground (complex enough to capture patterns, simple enough to generalize).

## Train / Validation / Test Split
- **Training set:** used to learn model parameters.
- **Validation set:** used for model selection and hyperparameter tuning.
- **Test set:** used ONLY for final, unbiased evaluation.
- Why 3 sets, not 2: tuning repeatedly against the test set directly would leak information and cause overfitting to the test set itself — making reported performance overly optimistic and not representative of real-world results.

---

# Domain 2: Evaluation Metrics

## Precision
Out of everything predicted positive, how many were actually positive.
Formula: TP / (TP + FP)
Prioritize when: false positives are costly.
Example: Spam filter — a false positive (real email marked spam) can cause missed business opportunities, OTPs, critical notifications.

## Recall
Out of everything actually positive, how many did the model catch.
Formula: TP / (TP + FN)
Prioritize when: false negatives are costly.
Example: Cancer detection — missing an actual patient (false negative) is far more dangerous than a false alarm.

## F1 Score
Harmonic mean of precision and recall — a single number that punishes a model where one of the two is very low, even if the other is very high (unlike a normal average, which lets a high score hide a low one).
Why it matters: precision and recall often trade off against each other; F1 prevents "gaming" the metric by sacrificing one for the other.

## RMSE (Root Mean Squared Error)
Used for **regression** problems (predicting a number, e.g. price, temperature) — not classification.
Steps:
1. Calculate error per prediction (predicted − actual).
2. Square each error (stops positive/negative errors from canceling out to a false "0").
3. Average the squared errors → this step alone = MSE.
4. Take the square root of that average → brings the unit back to something real and interpretable (e.g., "₹ lakh" instead of meaningless "lakh²").

## Confusion Matrix
|  | Predicted Positive | Predicted Negative |
|---|---|---|
| **Actual Positive** | True Positive (TP) | False Negative (FN) |
| **Actual Negative** | False Positive (FP) | True Negative (TN) |

- **False Positive:** actually negative, predicted positive (e.g., real email predicted as spam).
- **False Negative:** actually positive, predicted negative (e.g., real spam predicted as normal mail).
- Precision and Recall formulas come directly from this table.