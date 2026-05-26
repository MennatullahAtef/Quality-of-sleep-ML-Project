# Predicting Sleep Quality Using Machine Learning

Have you ever wondered exactly how much your daily habits affect how well you sleep? I built this end-to-end machine learning pipeline to answer that exact question. Using lifestyle data and daily tracking metrics, the model predicts whether someone will experience a "Good" or "Poor" night of rest.

## 🧠 Personal Reflection & What I Learned
I chose to focus on variables like sleep duration, active minutes, and stress levels because they represent things we can actually control in our day-to-day lives. While physiological data like heart rate is interesting, tracking how behavioral changes directly influence sleep quality felt much more practical and impactful.

**Key takeaways from this project:**
* **Data isn't clean by default:** Managing missing rows taught me how critical data preprocessing is. Filling missing data with column medians was a great lesson in preserving data distributions without inserting artificial bias.
* **Feature engineering makes the difference:** Simply feeding raw columns into an algorithm doesn't always yield strong results. Creating the `Stress_to_Activity_Ratio` was an absolute turning point for this model's ability to pick up on meaningful sleep patterns.
* **Hyperparameter tuning pays off:** Watching the model score jump up to its final performance metrics after running GridSearchCV proved to me just how powerful proper optimization can be.

## 📈 Model Performance
To get the most accurate predictions, I trained a Random Forest Classifier and fine-tuned it using GridSearchCV. 
* **Final Precision:** 0.79
* **Final Recall:** 0.79 
*(Both scores easily clear our project's baseline target of 0.3!)*

## 🛠️ Project Steps

1. **Defining the Goal:** Set up the main objective to study how factors like stress, exercise, and sleep hours interact to determine overall sleep quality.
2. **Cleaning the Data:** Scanned the raw dataset for missing fields and filled any gaps using column medians so the data remains balanced and complete.
3. **Exploring Patterns (EDA):** Created 5 different types of charts to study the relationships between 6 key lifestyle variables. This helped uncover exactly how sleep patterns behave before throwing them into an algorithm.
4. **Feature Engineering:** Designed a brand new metric called `Stress_to_Activity_Ratio`. This combines stress levels and active minutes mathematically, giving the model a much clearer feature to learn from.
5. **Model Tuning:** Tested 3 separate algorithms (Logistic Regression, Random Forest, and Gradient Boosting). Random Forest performed the best, so I used GridSearchCV to find the perfect hyperparameter settings.
6. **Final Evaluation:** Validated the model against a separate testing set and printed a full classification matrix to confirm the 0.79 accuracy.

## 📦 What's Inside This Repository
* `Sleep_Quality_Project (2).ipynb` – The complete Jupyter Notebook containing all the code, clean-up steps, and data visualizations.
* `cleaned_sleep_data.csv` – The finalized dataset used to train our model.
* `best_sleep_model.pkl` – The saved, trained "brain" of our Random Forest model.
* `app.py` – A lightweight deployment framework script used to handle user inputs and generate real-time predictions.
