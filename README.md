# Brief Description of the problem at hand:

The goal of this hackathon is to create a robust model that accurately predicts whether a user belongs to the Health Professional (HCP) category and determines their specialization or classification using the ad server engine's data. The ad server logs provide essential information such as browser details, IP addresses, geographic locations, search patterns, website URLs, and other relevant data.
The model should classify users based on their user ID (userplatformuid) and ad server log, determining if they are an SMM (Social Media Manager) and predicting their uniqueness or distribution. The output consists of two parts:
1. Scoring Solution: Participants need to provide output data that includes the user ID, an IS_HCP binary flag (1 for HCP, 0 for non-HCP), and the classification (specific to HCP) if IS_HCP is true. This output data will be used to evaluate the model's quality.
2. Full Solution: In addition to the scoring solution, participants are required to include a field called TAXONOMY, except for cases not mentioned in the assessment. The complete solution should include the user ID, IS_HCP flag, and the Taxonomy field, indicating uniqueness or HCP taxonomy (applicable only when IS_HCP is true).
The input data comprises different types of information:
- Health Care Workers: Users in this category are identified as HCP, but their specific specialization or classification is unknown. - Private or Known SMMs in Taxonomy: These lines indicate that the user is an SMM (IS_HCP is true) and has a specialization mentioned in the Taxonomy field.
- Lines without SMM information: These lines may or may not be related to SMMs, and the objective is to predict whether they are SMMs and determine any exceptions.
Participants need to develop a model that can accurately classify users as HCP or non-HCP and predict the specific specialization or distribution of HCP based on the ad server data.


# Solution proposed and description:

The problem involves identifying Health Professionals (HCPs) and estimating their uniqueness from ad server logs using machine learning. The solution includes data
cleanup, feature engineering, model training and evaluation. Categorical variables are converted, and the data is split into training and test sets. Features are analyzed and modified, and new ones are created. Machine learning algorithms like logistic regression or random forest are chosen for classification. Models are trained and evaluated using metrics like accuracy and precision. HCPs are identified, and their expertise is predicted. The output includes user IDs, HCP flags, and taxonomy information. The model is delivered and tested with unseen data. Iterative improvement is done by monitoring performance, gathering feedback, and exploring advanced techniques. The solution enables the accurate classification of users as HCPs or non-HCPs and estimation of their expertise using ad server logs.


# Approach:

Firstly, we conducted an overview of the dataset, followed by the removal of irrelevant columns from the training and testing datasets. Subsequently, we performed label encoding on the categorical columns. Next, we addressed the presence of null values within the dataset. Moving forward, we proceeded with text processing, which involved removing stopwords and punctuation, resulting in a cleaned text. Following this, we applied count vectorization to the "keywords" column to prepare it for model training. The dataset was then split into "x" and "y," where "y" included the "taxonomy" and "hcp" features. We applied the train-test split to  repare the data for modeling. We constructed a model using the random forest classifier within a multi-output classifier framework. The model yielded an accuracy of approximately 83%. Finally, we made predictions on the "x" test data and saved the results in a CSV file.
