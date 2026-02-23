# VIP_project
This is a data study on cancer and lifestyle habits, starting in the spring semester of 2026.


# (Chanyoung Shin, 02/13/2026)
## 1.models
Cox Proportional Hazards Model 
Very similar to logistic regression analysis, which is also used in machine learning (but in machine learning, it is used for prediction, not analysis).

Logistic regression is an analysis method that focuses on the event itself, but the cox analysis model focuses on time (e.g. survival period). That is,

In this equation, h0 represents the probability that an event will occur at time t when there are no arguments. h1 represents the probability that an event will occur at time (t) when there are arguments x1, x2, and x3. (Here, x1, x2, and x3 refer to smoking status in the paper.)

Questions or next to do: The Cox model appears to be a simple linear model, but it seems incapable of properly explaining highly complex and irregular data. It might be worthwhile to look for papers that apply nonlinear methods to this model.

Causal Mediation Analysis
This is a model that mathematically decomposes the path through which the outcome is affected.
to do next: Since this is a model I am seeing for the first time, I need to study it in depth and investigate whether there are any more advanced models.
Multiple Imputation by Chained Equations
A statistical machine learning model for data preprocessing, helping to address missing data.

next to do: There are many studies showing that GAN-based deep learning models like GAIN outperform MICE, so we can consider using a more advanced model for our project.



## 2.wish list
Nutrition 
New nutrition pyramid graphic really, healthy? 
(BMI）

Physical Activity 
Does too much high-intensity exercise cause cancer?

Restorative Sleep 
SLPFALL (Trouble falling asleep): "During the past 30 days, how often have you had trouble falling asleep?"
Values: 1 (every day), 2 (most of the time), 3 (sometimes), 4 (rarely), 5 (never)
SLPSTAY (Trouble staying asleep): "During the past 30 days, how often have you woken up in the middle of the night?"
SLPMED: "During the past 30 days, how often have you taken medication to help you sleep?”

Stress Management
ANXEV (Whether or not you have an anxiety disorder), DEPEV (Whether or not you have depression)

Avoidance of Risky Substances
MJEVER: "Have you ever used cannabis (marijuana, hashish) at any time in your life?

Positive Social Connection
Differences in cancer incidence between people who work and those who only work from home

etc.
​VIRAPP12M (Virtual Appointment)
URBRRL (Urban/Rural Classification)
REGION: (Northeast, Midwest, South, West).
DELAYR_Trans

about cancer
CANCERev: "Have you ever been diagnosed with cancer in your lifetime?" (1: Yes, 2: No)
CNKIND: "What type of cancer?" (Cancer patients only)
Caution: Starting in 2024, cancer type may be broken down into separate variables, such as CNKIND_Lung and CNKIND_Breast. Please check.
CANAGE: "How old were you when you were first diagnosed with cancer?”

3.What is lifestyle medicine?
Lifestyle medicine is an evidence-based medical specialty that applies therapeutic lifestyle interventions to treat, improve, and prevent chronic diseases such as diabetes.

Lifestyle Medicine has six main pillars.
Nutrition 
Physical Activity 
Restorative Sleep 
Stress Management
Positive Social Connection
Avoidance of Risky Substances




# 02/20/2026 labnote(Chanyoung Shin)

Questionnaire selection criteria:While examining the variables in the questionnaire, a question arose: Are people who take medication to correct unhealthy factors actually less likely to develop cancer than those who do not have these unhealthy factors? 
Therefore, I collected variables for those who simply have unhealthy factors and those who have taken or are taking medication for these factors.

## SLEEP FACTOR
  I collected variables regarding whether or not there were problems with sleeping, and whether drugs such as sleeping pills or marijuana were used to help with sleep.

## STRESS OR MENTAL FACTOR
 I collected variables regarding the presence or absence of mental health issues, such as anxiety disorders, and whether or not the participants were taking medication or receiving counseling to address their anxiety disorders. This could be particularly valuable for analyzing cancer incidence and post-cancer survival rates for individuals without a history of mental disorders, individuals with mental disorders who were treated for anxiety disorders with medication or specific methods, individuals who were treated with medication, and individuals who were treated with counseling.
