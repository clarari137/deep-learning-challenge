# deep-learning-challenge

## Neural Network Model Report
1. **Overview of the analysis:** This analysis examines a dataset of organizations that have received funding from a nonprofit, Alphabet Soup, and whether or not their venture had success. We are applying deep learning methods to help Alphabet Soup determine which organizations are more likely to be successful, predicting the outcome before Alphabet Soup grants the funding. 
   
3. **Results:** Using bulleted lists and images to support your answers, address the following questions:
- Data Preprocessing
  - What variable(s) are the target(s) for your model?
    - The target for this model is the column "IS_SUCCESSFUL", which identifies if the money was used effectively and the venture had success. 
  - What variable(s) are the features for your model?
    - The features are the variables we are using to predict the target outcome. This includes all columns excluding the identification columns ("NAME" and "EIN"). "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", "ASK_AMT" are all applicable columns, however during the optimization phase I experimented with dropping "SPECIAL_CONSIDERATIONS". "USE_CASE", "SPECIAL_CONSIDERATIONS", and "ASK_AMT" refer to the grant application, while the other variables center on the organization making the request. 
  - What variable(s) should be removed from the input data because they are neither targets nor features?
    - Variables to be removed include the identification columns, "EIN" and "NAME".
- Compiling, Training, and Evaluating the Model
  - How many neurons, layers, and activation functions did you select for your neural network model, and why?
    - Originally, I used 5 neurons, a number between the output layer (1) and input dimension (number of columns in the X_train dataset). I used two hidden layers and one output layer, with "relu" and "sigmoid" functions respectively.
  - Were you able to achieve the target model performance?
    - I was not able to achieve target performance. 
  - What steps did you take in your attempts to increase model performance?
    - In optimization, I tried dropping an additional column ("SPECIAL_CONSIDERATIONS", "USE_CASE"), adding an "Other" bin for "ASK_AMT", increasing the number of hidden layers from two to three, and increasing the number of nodes from 5 to 10 and eventually to 16 for the first layer. The highest accuracy score came from using two hidden layers with nodes 16 and 10 respectively, both dropped columns, and more strict cutoffs for the classifications binning. This accuracy score was still only 73.0%.
3. **Summary:** Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.
  Overall, the optimized model could predict the success of an organizations application for funding correctly 73% of the time. Although my optimization attempts were unsuccessful, I think that increasing nodes in conjunction with increasing the layers may have a good outcome due to the added complexity of the model. Further, improving the quality or amount of training data could also lead to a more accurate model.

## Sources
For this challenge, I used in class activities from the Neural Network module. I also referred to the links below for more clarity and explanation about the model we were working on. 
- https://stackoverflow.com/questions/43676678/how-to-calculate-input-dim-for-a-keras-sequential-model
- https://stats.stackexchange.com/questions/181/how-to-choose-the-number-of-hidden-layers-and-nodes-in-a-feedforward-neural-netw
- https://analyticsindiamag.com/a-complete-understanding-of-dense-layers-in-neural-networks/#:~:text=Units%20are%20one%20of%20the,dimensionality%20of%20the%20output%20vector
- https://machinelearningmastery.com/save-load-keras-deep-learning-models/
