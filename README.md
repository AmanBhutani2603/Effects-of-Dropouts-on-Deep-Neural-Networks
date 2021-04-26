**Effects of Dropouts on Neural Networks**

The main goal of the project is to study the effects of dropouts on the two specific fields of Deep Learning i.e Image Classification and Text Classification in order to achieve this goal we focus on the two main areas of a Neural Network namely “Effects on Model Parameters”, and “Effects on Feature Learning”. Model Parameters include the parameters based on which the performance of the model is judged here we have included six model features in our study namely Accuracy, Loss, Precision, Recall, ROC-AUC, and Learning Curve. 	In order to study the effects on feature learning, we use the concept of LIME(Locally Interpretable Model Agnostic Explanations). LIME in essence tells for a trained model that given a prediction made by the model what were the reasons for it to reach a particular decision, it treats any model fed to it as a black-box and for a given data sample it twerks the parameters of the model to record the effects on the prediction made by the model and hence tries to predict which parameters for a given sample were most important in giving a prediction. 

For Image Classification, we used MNIST and CIFAR-10 datasets which are Grayscale and RGB datasets respectively. And for Text Classification, we have used the IMDB Review dataset. Various experimental setups were created in order to study the above-mentioned effects but in the big picture following were the steps taken to conduct the studies:
Create the model pertaining to the dataset and whose features on which effects are to be studied i.e Feed-Forward or Convolutional Neural Networks
Models created range from the dropout rates 0.0 to 0.9
Models are trained on the needed dataset and its effects on the Learning curve are recorded
During Test-Time analysis other model parameters are recorded to study effects on them
LIME is used if needed to study the features most effective in the predictions made and draw relations between interpretability and dropout rates.

**Image Classification**

   **For MNIST Dataset**
   
  In order to study the effects of dropouts for the MNIST dataset, both Feed-Forward and Convolutional Neural Networks were used. To pre-process the dataset the labels of the   images in both training and testing datasets were converted into categorical variables and hence the output array size for the train and test set were 50,000 x 10 and 10,000 x 10 respectively. The pixel data of the image ranged from 0 to 255 and hence to efficiently train the model pixel values were normalized between 0 to 1.


  **Effects on Model Parameters of CNN**
  
  On training the models on the MNIST dataset the following results were obtained on the convolutional neural network:
	    
   1. For learning curve: It was observed that the model created better fit with the increase in the dropout rate until p = 0.3, after reaching a threshold the model became less complex and the gap between the plots of training and cross-validation accuracy increased and the accuracy on the training dataset decreased as the dropout rate went beyond 0.3.

   ![0 0_Acc](https://user-images.githubusercontent.com/48019495/116076615-144e5700-a6b2-11eb-8695-bb816eaefae5.png)   ![0 3_Acc](https://user-images.githubusercontent.com/48019495/116076635-1b756500-a6b2-11eb-8b60-71f6cb651d3a.png)


  ![0 6_Acc](https://user-images.githubusercontent.com/48019495/116076674-2b8d4480-a6b2-11eb-944c-20e805bbd15a.png)  ![0 9_Acc](https://user-images.githubusercontent.com/48019495/116076724-3c3dba80-a6b2-11eb-9e67-185c4b06ba8a.png)


 2. Accuracy: Model gave the best accuracy at the dropout rate 0.3. After which the accuracy decreased beyond p = 0.3.

![Accuracy](https://user-images.githubusercontent.com/48019495/116076803-57a8c580-a6b2-11eb-874d-a6b91cbd3000.png)

3. Precision: Highest value for precision was observed at p = 0.3 which was equal to 0.9843. It is observed there is a sudden drop in the precision for dropout value 0.8 to 0.9 which was equal to 0.116. 

![Precision](https://user-images.githubusercontent.com/48019495/116076908-7b6c0b80-a6b2-11eb-9575-12cac36b9d8d.png)

4. Recall: Highest Recall was observed at the dropout rate of 0.3 which is equal to 0.9757.

![Recall](https://user-images.githubusercontent.com/48019495/116076967-8d4dae80-a6b2-11eb-8dad-14f2399158f2.png)

5. Loss: Lowest value for loss was obtained at p = 0.3 which was equal to 0.0697.


![Loss](https://user-images.githubusercontent.com/48019495/116076843-65f6e180-a6b2-11eb-9070-1f7f7b747a19.png)

6.  ROC-AUC: Highest value of ROC-AUC was obtained when no dropout was applied on the model. Since, the rest of the parameters have their optimum values at p = 0.3 and also the ROC-AUC of dropout rate 0.3 is quite close to p = 0.0 it would be the best approach to use a dropout rate of 0.3.

![ROC-AUC](https://user-images.githubusercontent.com/48019495/116077144-c423c480-a6b2-11eb-98a7-d406ba6d04f5.png)
