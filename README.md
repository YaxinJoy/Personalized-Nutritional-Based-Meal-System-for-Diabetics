# Personalized-Nutritional-Based-Meal-System-for-Diabetics

### **Abstract** 

Diabetes is a common chronic disease, which was the eighth directing factor of death in 2020 with over 1.5 million deaths caused by it. The World Health Organization indicates that diabetes can be avoided or delayed with proper diet treatment. In this context, a food recommendation system specialized for diabetic patients would be a useful tool. Over the past several decades, recommendation system has changed remarkably with research proposing boosted computational models using nutritional and user information. This paper describes the implementation of a food recommendation system model based on the research work of Year et al., which provides a daily meal plan considering nutritional and personal parameters. The system starts with the pre-filtering stage which uses AHPSort to extract food suitable for diabetic patients generally, followed by an intelligent stage which receives user profile as input to generate both nutritional and personal meal plans for the user. A simulated case study is also developed for testing the system performance.

### **3 stages of the model**: 

1. Data preparation and cleaning

  The food data is collected from **USDA National Nutrient Database** (retrieved from [Kaggle](https://www.kaggle.com/datasets/haithemhermessi/usda-national-nutrient-database)). 
  The food data is cleaned by using AHPSort (multi-criteria decision analysis tool) to filter out food that is not suitable for diabetic patients.
  
  The user data is generated randomly. It records the gender, age (18~50), height (female: 150~175, male: 160~185， unit: cm), weight (female: 40~70, male: 50~80, unit: kg), and the food information he/she has taken (ID, name, frequency), last consumed time for each taken food.
  
2. Data processing 

  The user data generated in the last stage will be used as input in this stage. The system will first generate an initial weight table for each user. The value in each weight table will be changed based on the input. The weight table describes the weight of a user's preference for each food.

  The system first randomly generates a daily meal plan (breakfast, lunch, dinner), filters the plan based on user BMR value, and then computes the recommended plan based on the weight table. By following these steps, the system is ensured to consider both nutritional knowledge and user preferences.
  
  I also develop a simulated case study to add recent activities to one target user who is randomly chosen. The system traces 3 months of user activities and the average preference value is xxx, which is similar to the theoretical value provided by the research work of Yera et al.

3. Final Recommendation

  In this stage, the system generates recommended plan for each user in the record. Due to computational limit, I only run first time (which means no updated user activities as in the case study), thus the system only generates the initial meal plan for each user.
