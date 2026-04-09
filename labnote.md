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

# 2/23/2026 labnote (Chanyoung Shin)
I wrote a source code to count the number of data in each variable of Excel data. Looking at the results, it seems that there is a typo in the Excel variable name or my sample data is incorrect.
https://github.com/chanyoung-shin/VIP_project

# 3/06/2026 labnote(Chanyoung Shin)
Last week, I mentioned that the program couldn't load certain variables. That wasn't because the dataset was incorrect or there were typos. The variable names in the questionnaire and the dataset are different! For example, if there's a variable named WEIGHT, it's divided into WEIGHT_A and WEIGHT_B. Typically, _A represents variables for adults, _B and C represent variables for children, not adults. This information is available in the NHIS website's codebook.

# 3/12/2026 labnote(Chanyoung Shin)

Based on the 2022 codebook, I've reviewed the following variables in Google Sheets: SEX_A, AGENO, NEWNATORG_A, NEWRACE_A, RACEOTHER_A, EDUC_A, PHSTAT_A, CANEV_A, CANKIND1_A, CANAGE1_A. However, more discussion seems necessary before extracting the data.

SEX_A -> Use as is.
EDUCP_A -> Use as is.
PHSTAT_A -> Use as is.
NEWRACE_A / RACEOTHER_A -> Use the RACEALLP_A variable.
NEWNATORG_A -> Use the HISDETP_A variable.
CANAGE1_A, CANKIND1_A -> Dozens of variables are stored by cancer type, rather than using the NHIS questionnaire variables as is. Variables are divided from pages 51 to 100 (e.g., lung cancer, blood cancer, age under 85 when diagnosed). If we want to use this data, we can combine all variables and then use our method of assigning numbers to each variable individually.

AGENO -> Not in the codebook. It's not simply a number from 1 to 120, but rather a question about whether the person is over a certain age. There are variables for AGE65, AGE18 (not in the codebook), and AGEP_A. Therefore, it seems likely that you should use the AGE65 or AGEP_A variables instead.

# 03/23/2026 Chanyoung Shin’s labnote
My Python program indicates that it cannot extract the two variables 'MODN_A' and 'MODTP_A'. All other variables load successfully. 
Upon directly opening and checking the CSV file, it indicates that two variables could not be found; it appears that the variable names are incorrect.

 'MODN_A->MODNR_A,  MODTP_A-> MODTPR_A

# 03/27/2026 Chanyoung Shin’s labnote
I have discovered a useful variable. I recall that we previously decided to conduct our analysis by grouping subjects into just two categories—whether or not they had cancer—rather than distinguishing between specific types of cancer. However, instead of needing to consolidate the 30 separate cancer-related variables, it appears we can simply utilize the variable `NUMCAN_A`; this variable indicates the total number of times an individual has been diagnosed with cancer over the course of their lifetime.
