# Gym-Data-Set-Coursera-Capstone
Coursera Data Analyst Capstone
Nicholas A. Jojola 2025-09-10

Introduction
In this theoretical setting I will be acting as a data analyst for a fitness company looking to improve their recommendations for new members based on their fitness goals.

Clean
In data cleaning we started with data uniformity, converting column names and character data points into lowercase as well as trimming any unnecessary values e.g. hidden spaces.

Next, we re-coded the gender column to ensure all factors were either male or female, converting possible data points “m” to male, and “f” to female.

We then converted the age column to integers in the case that information was entered into as a type that may not be recognized later in our exploration.

Finally, we filtered age to only include the age range of 10-100, and weight to only include 60-600 lbs. as anything outside of these would most likely be a mistakes or outliers and of course dropped any duplicate entries.

QC: Missingness and Uniqueness by Column

column

n_na

n_unique

age

0

42

gender

0

2

weight_kg

0

532

height_m

0

51

max_bpm

0

40

avg_bpm

0

50

resting_bpm

0

25

session_duration_hours

0

147

calories_burned

0

621

workout_type

0

4

fat_percentage

0

239

water_intake_liters

0

23

workout_frequency_days_week

0

4

experience_level

0

3

bmi

0

771

weight_lb

0

532

hours_per_week

0

297

Explore
In this section, we will investigate the relationships between demographic and behavioral factors—such as gender, workout type, and weekly exercise duration—and key health outcomes including body fat percentage, estimated cardiovascular fitness. Our goal is to identify meaningful patterns that may inform recommendations for new gym members based on their fitness goals.

Body Fat and Workout Type
As you can see from the scatter plots there is a clear and distinct negative correlation between body fat percentage and hours per week spent in the gym.

HITT and cardio show the strongest negative correlation between hours of exercise per week and body fat. Strength and yoga show a strong negative correlation as well, however not as profound.

There doesn’t seem to be any significant correlation between body fat percentage and max BPM.

There is a clear difference in body fat between men and women as expected due to biological differences between the two group; women on average having naturally higher body fat percentages.

Summary by Gender × Workout Type

gender

workout_type

n

hours_median

hours_IQR

bpm_median

fat_median

fat_IQR

female

cardio

126

3.84

2.6325

182

29.2

6.275

female

hiit

107

4.14

2.4900

179

28.8

5.900

female

strength

123

4.00

2.6500

177

29.4

6.650

female

yoga

106

4.26

3.0500

180

28.1

10.800

male

cardio

129

3.99

2.7400

178

23.8

6.200

male

hiit

114

4.11

3.5250

183

23.2

11.750

male

strength

135

4.04

2.5350

180

24.4

6.750

male

yoga

133

3.84

2.7600

182

24.0

6.100


Box Plots
In the box plots we can see that the median body fat percentage across all workout types are insignificant; however, HITT has a much wider spread indicating that there is a larger variability among this group, further exploration is needed to see if this spread is due to other factors. 
Regression
In the regression coefficient table below we can see that holding the workout type variables constant, gym goings can expect an estimated 1.9% decrease in body fat per hour they spend in the gym each week with no statistical significance between groups.

Regression Coefficients: Fat % Model

term

estimate

std.error

statistic

p.value

conf.low

conf.high

Intercept

36.132

1.985

18.203

0.000

32.237

40.027

Male (vs Female)

-5.212

0.250

-20.825

0.000

-5.704

-4.721

HIIT (vs baseline)

-0.216

0.359

-0.602

0.547

-0.920

0.488

Strength (vs baseline)

0.625

0.344

1.814

0.070

-0.051

1.301

Yoga (vs baseline)

-0.069

0.351

-0.197

0.844

-0.759

0.621

Hours per week

-1.921

0.058

-33.398

0.000

-2.034

-1.808

Max BPM

-0.001

0.011

-0.059

0.953

-0.022

0.021

Model Fit: Fat % Model

r.squared

adj.r.squared

sigma

df

p.value

AIC

BIC

0.615

0.613

3.895

6

0

5416.406

5455.449

Interpret
From our analysis we can confidently say that body fat percentage is highly correlated with hours spent per week exercising regardless of workout type with the most variation in HITT workouts

We were unable to find any significant correlation between workout types and cardiovascular health although our data being limited to a single point in time.

Communicate
Based on our findings we can conclude that hours per week and body fat percentage are strongly correlated. This can give an initial recommendation for spending more time exercising and allow new gym members what to expect from exercise in general.

To discover fat loss and cardiovascular health we will need too collect more data to give our clients better recommendations.

Act
Our next steps would be to train implement programs for new gym members looking to lose body fat to spend more time exercising.

Suggestions would be meeting with personal trainers and sign up for classes such as HITT and yoga that keep new gym members structure and accountability.

Lastly. we will want to collect more data and continue our analysis to give more new gym members for advanced recommendations.
