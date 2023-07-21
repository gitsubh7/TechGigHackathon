# Brief Description of the problem at hand:

The goal of this hackathon is to create a robust model that accurately predicts whether a user belongs to the Health Professional (HCP)
category and determines their specialization or classification using the ad server engine's data. The ad server logs provide essential
information such as browser details, IP addresses, geographic locations, search patterns, website URLs, and other relevant data.
The model should classify users based on their user ID (userplatformuid) and ad server log, determining if they are an SMM (Social Media
Manager) and predicting their uniqueness or distribution. The output consists of two parts:
1. Scoring Solution: Participants need to provide output data that includes the user ID, an IS_HCP binary flag (1 for HCP, 0 for non-HCP), and
the classification (specific to HCP) if IS_HCP is true. This output data will be used to evaluate the model's quality.
2. Full Solution: In addition to the scoring solution, participants are required to include a field called TAXONOMY, except for cases not
mentioned in the assessment. The complete solution should include the user ID, IS_HCP flag, and the Taxonomy field, indicating uniqueness
or HCP taxonomy (applicable only when IS_HCP is true).
The input data comprises different types of information:
- Health Care Workers: Users in this category are identified as HCP, but their specific specialization or classification is unknown.
- Private or Known SMMs in Taxonomy: These lines indicate that the user is an SMM (IS_HCP is true) and has a specialization mentioned in
the Taxonomy field.
- Lines without SMM information: These lines may or may not be related to SMMs, and the objective is to predict whether they are SMMs and
determine any exceptions.
Participants need to develop a model that can accurately classify users as HCP or non-HCP and predict the specific specialization or
distribution of HCP based on the ad server data.
