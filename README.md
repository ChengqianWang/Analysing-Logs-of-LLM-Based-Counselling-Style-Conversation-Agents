# Analysing-Logs-of-LLM-Based-Counselling-Style-Conversation-Agents

Source of Data: 
Meyer, S., & Elsweiler, D. (2024, March). " You tell me": a dataset of GPT-4-based behaviour change support conversations. In Proceedings of the 2024 Conference on Human Information Interaction and Retrieval (pp. 411-416).
osfstorage-archive(https://osf.io/c9nvm/overview)

We save the environment we have exported the complete Python environment configuration file, named environment.yml.

1.	We start our work on the “user_preprocessed.csv” and “turn_preprocessed.csv” from osfstorage-archive(https://osf.io/c9nvm/overview).

2.	Dataset clean process was included in file “One_Dataset Clean.ipynb” and “Two_Dataset Clean.ipynb”. After cleaning, user information was exported as “explore_user_common.csv”, dialogue information was exported as “explore_turn_common.csv”.

3.	Sentiment analysis using Stanford CoreNLP was included in file “Three_CoreNLP API_user_sentiment&bot_sentiment.ipynb”, the results were saved to ‘user_sentiment’ and ‘bot_sentiment’ columns in file “explore_turn_common.csv”.

4.	In “Four_Trim to 12 turns & LIWC LSM & Empath LSM.ipynb”, we processed the structure for LIWC_LSM analysis by extract each turn out into independent file, and those turn files are save in “turn_csvs” folder, LIWC LSM was analysed was not conducted in jupyter notebook. Instead, we use LIWC-22 software, and the LIWC LSM result were saved in “turn_csvs/LSM Result”. Empath LSM was done in this file, and result were saved in file “explore_turn_12.csv”

5.	In file “Five_Target Behaviour Identify.ipynb” we identified what the target behaviour in each dialogues for user, we assigned “sustainable living, healthier eating, less procrastination” to each dialogue using gpt-3.5-turb. And the result were saved in “target_behaviour_identification.csv”.

6.	In folder “comparison analysis”, we did linguistic cues comparison based on each user perceived measures. We used perspectives like utterance length, sentiment distribution, Empath LSM and LIWI LSM.

7.	In folder “TopicGPT analysis”. 

In “One_Topic_Generation.ipynb” we generated 219 row topics using gpt-4, the results were saved in “raw_generated_topics.txt”, for further analysis, we convert this txt file to “generated_topics.csv”.
In “Two_Topic_Deduplication.ipynb” we deduplicated topics by clustering over embeddings of the generated topic descriptions, results were saved in “topics_after_deduplication.csv”.
In “Three_Topic Assignment.ipynb”, we employed the GPT-4-turbo model to assign topics to individual dialogues, results were saved in topics_assigned.csv

8.	In folder “TopicGPT analysis/Analysis&Visualisation”.
In “PCA_Composite Quality Score.ipynb”, we select the most representative user perception metrics, informed by our VIF analysis of user experience measures, we treat readiness to change (RC) as the primary outcome for topic-based analysis.
In “Topic Analysis.ipynb”, we generated figures showing distribution of topics for conversations under no system setting and under framework with less procrastination as goal, we made comparisons between high score and low score based on Readiness to Change (Delta).
