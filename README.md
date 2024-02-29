# MyThesis
##  Optimizing LSTM and Bi-LSTM for Medical Scope SIBI Sign Language Word Detection with Landmark Reduction
Sign language is available as a means of communication, difficult to understand, making social interaction difficult for those with hearing loss. So a sign language translator system is needed that is able to help communication with hearing impaired people. Therefore, a sign language translator system is needed that can help communication between people with hearing loss and normal people. In this research, landmark reduction is implemented on LSTM and Bi-LSTM to optimize the detection of medical SIBI sign language consisting of the sign words “Batuk”, “Demam”, “Gigi”, “Kepala”, “Minum”, “Obat”, “Perut”, “Resep”, and “Sakit”. **Landmark reduction is a method of reducing landmarks by selecting landmark points based on literature studies related to landmark components used in sign language**. Based on the test results, the application of landmark reduction to LSTM and Bi-LSTM is effective in improving accuracy and reducing loss in training, but not effective in accelerating convergence in training. In addition, the k4 landmark reduction where the model processes the landmarks of both hands, upper body, and mouth is able to increase the accuracy of the LSTM model from 0.6889 to 0.8667 and Bi-LSTM from 0.8111 to 0.9333.

### About Landmark Reduction

### About Dataset
The dataset was collected by taking recordings of sign language movements based on the guidelines of the digital [SIBI dictionary](https://pmpk.kemdikbud.go.id/sibi/) from the Indonesian Ministry of Education and Culture. Recordings were taken using an Apple iPad Pro (5th generation) camera with specifications 12MP, f/1.8, (wide), 1/3", 1.22µm, dual pixel PDAF, gyro-EIS. Recordings were taken with a distance of ± 1m between the camera and the respondent and a recording quality of 1080p 30 frames per second (fps). Respondents were asked to act out a gesture sentence between the words “Batuk”, “Demam”, “Gigi”, “Kepala”, “Minum”, “Obat”, “Perut”, “Resep”, and “Sakit” repeatedly five to ten times with different tempos. Performing the gesture sentences makes the beginning and ending position of each gesture word vary and the repetitive motion also makes the position of the landmark points vary every frame. After the recording data was collected, annotation was done by marking the beginning and end of each word frame using the [Label Studio application](https://labelstud.io/). Here is the amount of recorded data collected.

| Sign Word | Amount of Training Data | Amount of Test Data |
|:----------|:-----------------------:|:-------------------:|
|Batuk      |112                      |10                   |
|Demam      |102                      |10                   |
|Gigi       |113                      |10                   |
|Kepala     |113                      |10                   |
|Minum      |116                      |10                   |
|Obat       |120                      |10                   |
|Perut      |111                      |10                   |
|Resep      |116                      |10                   |
|Sakit      |113                      |10                   |

### Implementation Flow

### Model Architecture
* LSTM

* Bi-LSTM

### Results
* Train Results

| Model | Epoch | Avg Accuracy | Avg Loss |
|:------|------:|-------------:|---------:|
|LSTM (Without Landmark Reduction) |59|0,9805|0,2978|
|LSTM (K2 Landmark Reduction) |35|0,9878|0,0447|
|LSTM (K3 Landmark Reduction) |62|0,9854|0,2203|
|LSTM (K4 Landmark Reduction) |24|0,9902|0,036|
|LSTM (K5 Landmark Reduction) |29|0,9902|0,1056|

In this test, it can be seen that landmark reduction is able to increase the average accuracy value and reduce the average loss against LSTM without applying landmark reduction. However, applying landmark reduction does not always speed up the convergence of the LSTM model because in LSTM applying k3 landmark reduction to reach convergence requires 62 epochs, 3 epochs more than without landmark reduction.

| Model | Epoch | Avg Accuracy | Avg Loss |
|:------|------:|-------------:|---------:|
|Bi-LSTM (Without Landmark Reduction) |59|0,9805|0,2978|
|Bi-LSTM (K2 Landmark Reduction) |35|0,9878|0,0447|
|Bi-LSTM (K3 Landmark Reduction) |62|0,9854|0,2203|
|Bi-LSTM (K4 Landmark Reduction) |24|0,9902|0,036|
|bi-LSTM (K5 Landmark Reduction) |29|0,9902|0,1056|

* Test Results

| Without/With Landmark Reduction | Amount of Training Data | Amount of Test Data |
|:----------|:-----------------------:|:-------------------:|

### Demo

### Glossary

| Term | Definition |
|:-----|:-----------|
