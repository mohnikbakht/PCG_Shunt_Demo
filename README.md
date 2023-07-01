# Application of Acoustic Signals in Systemic to Pulmonary Shunts in Ductal Dependent Infants using Deep Learning

Congenital heart diseases (CHD) are birth defects that change the heart’s structure and blood flow. Patients with these conditions may require an artificially placed shunt to allow adequate circulation through the heart and lungs. Evaluating shunt function frequently, thus, becomes paramount to sustain the functionality and life of the shunt. Effective monitoring of the shunt flow requires a non-invasive, quantitative approach to enable frequent monitoring of the shunt’s condition. Leveraging machine learning approaches to differentiate systolic murmurs through shunts recorded using a stethoscope may provide such a tool. 

In this work, two deep learning architectures for classifying the auditory characteristics of blood flow through shunts are introduced focusing on six clinically-relevant tasks: (1) shunt type, (2) flow state on Extracorporeal Membrane Oxygenation (ECMO), (3) flow before and after shunt and/pr pulmonary artery angioplasty, (4) cyanosis compared to non-cyanosis, (5) flow over time, and (6) flow state in elevated pulmonary artery pressure. A CNN-LSTM (supervised) was trained and validated for task (1) reaching an F1 score of 0.88 (AUC=0.95). To address the limited sample size of the remaining tasks, a variational autoencoder (VAE) (unsupervised) was trained and validated for dimensionality reduction of the input samples, and its latent vector was used to train support vector machine (SVM), random forest, and a k-nearest neighbors (KNN) models for the remaining downstream tasks. For tasks (1)-(5) we reached AUCs of 0.77, 0.73, 0.86, 0.60, 0.81 respectively. Thus, for the first time to the best of our knowledge, we have demonstrated that the acoustic sounds recorded using a stethoscope from CHD patients contain information about changes in shunt flow.

## Architecture 

Overview of the supervised model. (a) an spectrogram image of the heart sound segment as input sample. (b) a CNN-LSTM classifier model to classify the spectrogram sample into shunt type classes. (c) Sano, and mBTTS+DAS as the two major shunt type classes of interest. CNN: Convolutional Neural Network; and LSTM: Long Short-Term Memory.

<p align="center">
<img src="https://github.com/mohnikbakht/PCG_Shunt_Demo/blob/main/figures/figure2.png" alt="Architecture figure" width="600"/>
</p>

Overview of the unsupervised model. (a) an spectrogram image of the heart sound segment as input sample. (b) VAE’s encoder outputting the normal distribution parameters. (c) the latent vector is sampled from the learned normal distribution (KL loss). (d, e) the decoder tries to reconstruct the input from the sampled latent vector (reconstruction loss). VAE: Variational Auto-encoder; and KL: Kullback–Leibler.

<p align="center">
<img src="https://github.com/mohnikbakht/PCG_Shunt_Demo/blob/main/figures/figure3.png" alt="Architecture figure" width="600"/>
</p>

## Results

Supervised model performance. (a) A receiver operating characteristic (ROC) plot and confusion matrix of the performance of the shunt type classifier model. (b) t-SNE plot of the output of the LSTM layer before the linear output layer color coded based on shunt type for the training and test set. LSTM:Long short-term memory.

<p align="center">
<img src="https://github.com/mohnikbakht/PCG_Shunt_Demo/blob/main/figures/figure4.png" alt="results figure" width="600"/>
</p>

Unsupervised model performance results for the remaining 6 tasks are presented in Table 1.

<p align="center">
<img src="https://github.com/mohnikbakht/PCG_Shunt_Demo/blob/main/figures/figure5.png" alt="results figure" width="600"/>
</p>

 ## Conclusion

Our preliminary data revealed, for the first time, that in fact “whooshing” of a systolic ejection murmur through a systemic to pulmonary connection is distinct based on the shunt type. In this work we developed supervised and unsupervised deep learning models to classify shunt type and patient conditions based on blood flow acoustics through shunts recorded using a digital stethoscope. Although acoustic signaling using machine learning and neural networking for murmur detection is not new, the application to characterizing shunt murmurs is novel. Therefore, the proposed work enables understanding of the shunt’s health in the context of a cyanotic single ventricle patient using a non-invasive approach.
