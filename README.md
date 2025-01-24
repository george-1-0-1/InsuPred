# InsuPred
Experimental LSTM approach on Insulin Prediction using HUPA Diabetes Dataset

Effective insulin management is crucial for individuals with diabetes, requiring accurate predictions for basal and bolus doses based on factors like glucose levels, activity, and food intake. This study presents a machine learning approach using Long Short-Term Memory (LSTM) networks to predict insulin needs from sequential data, including glucose levels, caloric intake, heart rate, steps, and carb inputs. The system uses the HUPA UCM Diabetes dataset, which contains time-stamped physiological and behavioral data. After preprocessing and normalization, the data is structured into sequences for time-series analysis, allowing the LSTM models to identify key patterns. The models are trained and evaluated with MAPE to ensure accurate predictions. This approach aims to improve diabetes management by offering a reliable tool for personalized insulin dosing.

## Dataset 

HUPA-UCM diabetes dataset 
https://www.sciencedirect.com/science/article/pii/S2352340924005262

Download dataset variant from https://data.mendeley.com/datasets/3hbcscwz44/1

## Proposed System Architecture
![image](https://github.com/user-attachments/assets/74b9cb4e-dd96-45f4-a046-79be685e5d4c)

## Experimental Results
The basal rate prediction model was evaluated using an LSTM-based architecture comprising three layers with dropout regularization and early stopping. Mean Absolute Percentage Error (MAPE) and loss curves were utilized as key performance metrics to assess the model's accuracy and generalization capabilities.

### A. Mean Absolute Percentage Error (MAPE) Analysis

The LSTM model achieved a training MAPE of 1.20% and a testing MAPE of 1.50%. 

![image](https://github.com/user-attachments/assets/cdca4aa3-bf15-4dc3-91e9-c4137c198b1e)

Fig. 2.	MAPE Analysis

These low MAPE values reflect the model's high predictive accuracy, which is noteworthy given the challenge of basal rate prediction due to input feature variability, such as glucose levels, heart rate, and activity data. The slightly elevated testing MAPE suggests minimal overfitting, a typical challenge with sequential models like LSTM. The graph (Fig. 2.) illustrates the Absolute Percentage Error (APE) for individual data points in a predictive model. APE varies from 2.00% to 6.67%, indicating prediction accuracy differences across points. The model shows generally low error levels, with only slight deviations, suggesting acceptable predictive performance and areas for targeted refinement.

### B. Loss Convergence

The training and validation loss curves demonstrate a smooth decline over 20 epochs, with validation loss tracking closely alongside training loss. This convergence pattern in Fig. 3 suggests effective learning of underlying data patterns without significant overfitting, achieving a 99.2% accuracy. Early stopping contributed to stable convergence by halting training when optimal performance was reached on the validation data.

![image](https://github.com/user-attachments/assets/1e82fdab-e876-4d16-9330-3949bc6596d6)

Fig. 3.	Loss Convergence Graph

### C. Model Generalization Capability

The marginal difference between training and testing MAPE suggests robust generalization. This performance is supported by the inclusion of time-based features (e.g., hour and day of the week), which enable the model to capture temporal patterns and cyclic trends in basal rate requirements.

### D. Architecture Efficiency

The LSTM model architecture as depicted in Fig .4, configured with an increasing-decreasing sequence of neurons (128-64-32), proved effective in modeling sequential dependencies. 

 ![image](https://github.com/user-attachments/assets/ac6d2c83-40e4-415b-9c4f-bb0073c676d7)

Fig. 4.	LSTM Architecture

Dropout layers with a 0.3 rate reduced overfitting while preserving the model's ability to learn complex patterns, as evidenced by the smooth convergence of training and testing losses and low MAPE scores.

### E. MAPE Comparison

 ![image](https://github.com/user-attachments/assets/281ab1cf-e5b3-482d-bb31-386e47d012a5)

Fig. 5.	MAPE Comparison Chart

A comparison of MAPE metrics between training and testing datasets reveals close values, underscoring the model’s stability across data splits. The MAPE bar chart illustrated in Fig. 5 highlights this consistency, affirming the model's reliability in practical basal rate prediction applications. The HUPA UCM Diabetes dataset [30] is a comprehensive resource designed specifically for advanced diabetes management research. Developed with the goal of supporting machine learning applications, this dataset includes a wide range of data types relevant to Type 1 and Type 2 diabetes management. The dataset comprises continuous glucose monitoring (CGM) readings, insulin dosing records (both basal and bolus), and a variety of lifestyle metrics such as dietary intake, physical activity, heart rate, and step counts. This extensive combination of physiological and behavioral data enables researchers to train predictive models, particularly LSTM networks, to accurately forecast blood glucose levels and insulin requirements.

A unique feature of the HUPA UCM dataset is its inclusion of patient-specific parameters such as insulin sensitivity and carbohydrate-to-insulin ratios, which vary among individuals and impact insulin dosing needs. These variables allow machine learning models to account for individual variability, improving prediction precision and creating more tailored insulin management strategies. The dataset also supports the development of real-time prediction models by providing time-stamped data, allowing researchers to examine temporal patterns that influence blood glucose fluctuations. Overall, the HUPA UCM dataset serves as a valuable asset for creating and testing machine learning models aimed at predicting insulin requirements. It facilitates a deeper understanding of diabetes dynamics and enables more accurate, patient-specific insulin dosing predictions essential for next-generation diabetes management systems.
