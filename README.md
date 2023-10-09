# IBM DATA SCIENCE CAPSTONE PROJECT

![GitHub last commit](https://img.shields.io/github/last-commit/byvfx/ibm_ds_capstone)

My final project for the Coursea IBM Data Science Certificate

## Table of Contents

- [Objective](#objective)
- [Data Exploratory](#data_exploratory)
- [Data Collection](#data_collection)
- [Predictive Data Analysis](#predictive_data_analysis)
- [Data Visualization](#data_visualization)
- [Present Findings](#present_findings)
  

## Objective 
### Space Y vs SpaceX

**Space Y**, a fictional competitor to **SpaceX** (founded by the billionaire industrialist **Allon Musk**), is set to enter the aerospace market. As part of the competitive strategy:

### 1. Launch Pricing Analysis
My primary task is to deduce the pricing structure of each launch. This involves:
   - Gathering comprehensive data about SpaceX.
   - Creating intuitive dashboards to share insights with my team.

### 2. Reusability Assessment
A key factor in cost efficiency is the reuse of rocket stages. I will:
   - Investigate if SpaceX plans to reuse its first stage for launches.
   - Extract patterns and insights to inform Space Y's strategies.

### 3. Predictive Modeling
Beyond manual analysis, I will leverage machine learning to forecast SpaceX's actions:
   - Train a predictive model on available public data.
   - Use the model to estimate if SpaceX intends to reuse the first stage for future launches.

This analysis will help **Space Y** strategize its market entry and potentially outpace SpaceX in the aerospace sector.


## Data Exploratory

In this phase, I'll be focusing on a crucial phase in data science: **Exploratory Data Analysis (EDA)**. My goals during this phase can be categorized into two primary objectives:

### 1. Understanding the Dataset
In my initial steps, I'll engage in a detailed EDA on a specific database. This exploration is intended to:
   - Familiarize myself with the intricacies of the data.
   - Identify inherent patterns.
   - Extract preliminary insights.

### 2. Identifying Predictive Attributes
With an overarching goal to predict the landing success of the Falcon 9’s first stage, I've observed:
   - Distinct attributes, like the success rates since 2013 and particular launch sites, may indicate landing outcomes.
   - Notable patterns among launch sites: 
     - **CCAFS LC-40**: A general success rate of 60%.
     - **KSC LC-39A & VAFB SLC 4E**: Varying success rates.
     - When considering launches with masses exceeding 10,000 kg, the success rate for CCAFS LC-40 jumps to 100%.

As I navigate this phase, I'm keen on:
   - Discovering correlations that might be hidden within the data.
   - Preparing the data for subsequent predictive modeling, which includes tasks like converting categorical data using methods like one-hot encoding.

By the conclusion of this phase, I aim to spotlight essential attributes. These insights will play a pivotal role in developing a machine-learning model designed to forecast the successful landing of Falcon 9’s first stage.

## Data Collection

In this phase, I'll be focusing on data collection using the **SpaceX REST API**. We're drawing from SpaceX launch data that offers details about launches, encompassing the rocket utilized, payload specifics, and both launch and landing particulars.

### Objective

Our primary objective is to predict if SpaceX will attempt a rocket landing based on the provided data. The data is accessed through various endpoints, but our main focus is on the endpoint `api.spacexdata.com/v4/launches/past`. To retrieve the data, a GET request is made, with the response being a list of JSON objects. Each item in this list represents an individual launch. This data can then be transformed into a more analysis-friendly flat table format using the `json_normalize` function.

### Additional Data Sources

Additionally, Falcon 9 Launch data can be gathered by web scraping specific Wiki pages. Here, the **Python BeautifulSoup package** proves invaluable, helping to extract data from HTML tables, which is then parsed into a Pandas data frame.

### Data Refinement Steps:

1. **Data Wrangling using an API**: 
   - Certain columns, like 'rocket', primarily contain ID numbers. To fetch more relevant data linked to these IDs, it's imperative to interact with other API endpoints such as Booster, Launchpad, payload, and core.

2. **Data Filtering**: 
   - Our dataset merges information from both Falcon 1 and Falcon 9 boosters. Hence, filtering becomes essential to ensure only Falcon 9 launch data remains.

3. **Handling Null Entries**: 
   - Inconsistencies in the data manifest as NULL values, especially in the PayloadMass column. One strategy to handle this is by determining the mean of the PayloadMass entries and substituting the null spots with this mean value.
   - The 'LandingPad' column, which uses NULL values to denote the non-use of a landing pad, will be addressed later with one-hot encoding techniques.

By the end of this phase, the goal is to have a structured and insightful dataset, optimized for further analysis.

## Predictive Data Analysis

In this segment, we'll dive deep into **Predictive Analysis**. Our focus will be on constructing a machine-learning pipeline aimed at predicting the successful landing of Falcon 9's first stage. The key steps in this journey are:

### 1. Preprocessing
- Standardizing the data ensures that the dataset is consistent and free from any outliers or discrepancies.

### 2. Data Splitting
- Leveraging `Train_test_split` to segregate the data into:
  - Training data, used to train the model.
  - Testing data, used to evaluate the model's performance.

### 3. Model Training & Hyperparameter Tuning
- Training our model on the available data.
- Implementing **Grid Search** to identify optimal hyperparameters, enhancing the algorithm's performance.

### 4. Model Selection
Multiple algorithms will be tested to identify the most accurate:
   - Logistic Regression
   - Support Vector Machines
   - Decision Tree Classifier
   - K-Nearest Neighbors
Using the best hyperparameter configurations, we'll determine which model performs the best with our training data.

### 5. Evaluation
- The final step involves visualizing the results using a **confusion matrix**, offering a clear picture of the model's accuracy and areas of potential improvement.

This structured approach ensures a comprehensive analysis, helping in making informed decisions based on data-driven insights.

## Data Visualization

Throughout our exchange, we delved into multiple facets of data science, spanning from **Exploratory Data Analysis (EDA)** to **Predictive Analysis**. At the heart of these processes lies the pivotal role of **Data Visualization**.

### 1. Understanding the Data

- Visualizing data is the precursor to any deep analysis or prediction. EDA involves grasping the intricacies of data, spotting patterns, and gleaning initial insights. Effective visualization tools and methods aid in making these patterns and anomalies apparent.

### 2. Dashboard Creation

- For competitors, such as the fictional entity **Space Y**, aiming to challenge stalwarts like **SpaceX**, the utility of dashboards is undeniable. These dashboards, powered by compelling visualizations, provide concise snapshots of crucial metrics, guiding teams towards informed decisions.

### 3. Machine Learning & Predictive Analysis

- As we explored the construction of a machine learning pipeline, particularly for predicting Falcon 9's landing success, the significance of visualizing model outcomes became evident. Instruments like confusion matrices offer a lucid representation of a model's accuracy, highlighting its strengths and potential areas of enhancement.

### 4. Model Selection & Evaluation

- When juxtaposing multiple algorithms, such as Logistic Regression, Support Vector Machines, or Decision Tree Classifiers, visual comparisons streamline the model selection process. Visual aids crisply demonstrate which model has the edge over others based on specific evaluation metrics.

In summary, while raw data and intricate algorithms constitute the structural foundation of data science, **data visualization** infuses these numbers with meaning, translating them into tangible insights. Whether the task at hand involves evaluating SpaceX's launch triumphs or crafting predictive models for imminent rocket landings, adept data visualization bridges the chasm between intricate data sets and actionable insights.

## Present Findings


In presenting my work, I recognize the transformative **power** of effective communication. As I navigate this journey, here are the key pillars I'm focusing on:

### 1. **Prioritizing Clarity**

- I introduce topics with clarity and precision.
- I break down complex ideas into digestible bullet points.
- I ensure a logical progression, leading my audience from one concept to the next.

### 2. **Emphasizing Visual Appeal**

- I harness the **power** of visuals, incorporating graphs, charts, and infographics.
- I maintain design consistency, from color schemes to fonts, for a cohesive appearance.
- I balance content and whitespace, preventing information overload.

### 3. **Incorporating Interactive Elements**

- I'm integrating interactive aspects, such as quizzes, polls, or hands-on demos, to engage my audience.
- Live coding demonstrations, facilitated by tools like Jupyter Notebooks or RStudio, are part of my toolkit.

### 4. **Crafting a Strong Narrative**

- I weave a compelling narrative around my data and discoveries.
- I highlight challenges, processes, and outcomes to take my audience on a journey.

### 5. **Leveraging the Power of Simplicity**

- While I possess deep technical knowledge, I understand the **power** of simplicity and ensure that comprehension remains central to my presentation.

### 6. **Establishing a Feedback Loop**

- I actively seek questions and feedback.
- I value open dialogues, knowing they can surface fresh insights and perspectives.

### 7. **Concluding with Impact**

- I summarize key points effectively.
- I aim to leave my audience with a powerful statement or question, sparking reflection and engagement.

In essence, my presentation isn't just a display of results. It's a conduit for sharing discoveries, insights, and knowledge. With the **power** of effective presentation, I aim to resonate, inspire, and leave a lasting impression.



