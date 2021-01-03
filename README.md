## Covid-19 CT Scan Prediction With Deep Learning

This project was done in collaboration with Zumari Chatham, Niket Pandya, John K. Kimutai, James Okullo and Youa Vang. The dataset was obtained from Kaggle and it is stored in a shared drive which can be accessed using the link below:
https://drive.google.com/drive/folders/1xdk-mCkxCDNwsMAk2SGv203rY1mrbnPB?usp=sharing

The purpose of this project was to find a pre-trained model that classified the images with high accuracy, then build our own model and compare its accuracy to champion pre-trained model. We trained six pre-trained models on the dataset with the same parameters and the same fully connected layers. The models we used were VGG16, VGG19, InceptionV3, Xception, ResNet50, and ResNet152. From our research, ResNet152 model had the highest accuracy of 95% when predicting the test dataset.

We then build our model with ResNet152 as the base model and attached an LSTM model to it. We trained the ResNet152-LSTM model with the same datasets and parameters, then we compared the result with the champion model, ResNet152. We conclude that the champion model was better at classifying covid and normal images. There are a few reasons why we think the Resnet152-LSTM model did not perform as well.

First, the Resnet152-LSTM is a much deeper model, so training took much longer. In our case, on average the training time doubled compared to the champion model. We built the ResNet152-LSTM model, hoping to get better results by combining the best model for our dataset with an LSTM model, but overall, the LSTM model yielded poor results. 

Second, LSTM is generally used to address sequence prediction problems in which the order on the observations must be preserved when training models and making prediction. The images collected from patients are taken in sequence from top-to-bottom and side-to-side of the diaphragm. These images are not a sequence of a progressing disease or event and, therefore, our dataset is not necessarily a sequence problem. If our dataset were images taken in consecutive days and showing progression of a disease, then it would be more of a sequence problem and therefore, the LSTM model may perform better, but that is not our case. 

Due to time constraint, we used the same parameters on all the models. Also, we didn’t have the time to make any modifications to any layers of ResNet152-LSTM model. We believe that if we had more time to adjust the model and test other parameters, then we could improve the Resnet152-LSTM model to have better accuracy on classification.  Overall, the experiment was successful because we were able to identify the best model at classifying COVID-19 for the dataset given the same conditions.

Also, during our research we used Grad CAM to analyze what the model sees at a given layer. One of the criticisms most often raised about neural networks is that they are 'black-boxes,' therefore, a big challenge with these models is model interpretability: "how are the "guts" of the model functioning, and are they functioning correctly?". GradCAM helps to visualize what areas or features the model uses to classify an image as either covid or normal. Using the gradients of specific classes flowing into the last convolution layer, Grad-CAM creates a heatmap that shows the regions of the image that are important for correct classification 

You can read more about this project here: [Covid-19 CT Scan Prediction With Deep Learning](https://github.com/youavang/Covid-19_CT_Scan_Prediction/blob/main/Covid-19%20CT%20Scan%20Prediction%20With%20Deep%20Learning.pdf)
