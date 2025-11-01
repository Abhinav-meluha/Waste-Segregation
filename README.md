# Waste-Management

**Overview**

Smart waste classification is the deep learning-based application of computer vision for classifying wastes into classes such as Biodegradable, Recyclable, and Hazardous. A transfer learning approach coupled with the architecture of MobileNetV2 has been used to attain high accuracy along with high computational efficiency. The proposed system is deployed on a Streamlit web interface to perform real-time recognition of wastes, thereby enabling smart city waste management.

**Introduction and Background of Research Findings**

Poor waste segregation has increasingly become a major challenge that highly impacts environmental sustainability and urban sanitation. Several works on this topic demonstrate that AI might substantively improve the accuracy and effectiveness of waste sorting in recycling systems.

Key Research Findings Influencing This Project: 
**Automation in Waste Management:** Various research indicates that AI and deep learning models perform much better when compared to a conventional manual sorting system in reducing classification errors and enhancing sorting speed. 
**Efficiency of Transfer Learning:** It has been indicated in literature that transfer learning with models such as MobileNetV2 or ResNet50 works quite effectively for environmental datasets which have limited images, reducing the need for large-scale retraining.
**Sustainability Impact:** Intelligent waste classification systems are directly aligned with the UN's Sustainable Development Goals, SDG 11, on sustainable cities and communities by promoting eco-friendly disposal and recycling.

**Dataset Preparation**

Data Collection and Structure:
The dataset consists of images of 10 different kinds of wastes: battery, biological, cardboard, clothes, glass, metal, paper, plastic, shoes, and trash. 
Hundreds of labeled images in each class were provided to represent real-world waste material.

**Data Preprocessing Steps:**

Data cleaning: Removed corrupted and/or unreadable image files.
Data Splitting: Data were split into 70% Training, 20% Validation, and 10% Testing.
Image Augmentation: Random transformations include: Rotation (±15°) Zoom (0.2) Horizontal flip Rescaling (1/255 normalization)
Image Resizing: The images were all resized to 224×224 pixels since that is the expected size for MobileNetV2.


**Model Design and Training**
Model Architecture: MobileNetV2;
Framework: TensorFlow / Keras;
Transfer Learning: Pre-trained on ImageNet and fine-tuned on a waste dataset.

Training Parameters:
| Parameter     | Value                                                 |
| ------------- | ----------------------------------------------------- |
| Optimizer     | Adam                                                  |
| Learning Rate | 0.001 (auto reduced to 0.0003 with ReduceLROnPlateau) |
| Loss Function | Categorical Crossentropy                              |
| Batch Size    | 32                                                    |
| Epochs        | 10                                                    |
| Metrics       | Accuracy                                              |

**Regularization Techniques:**
Early Stopping: This prevented overfitting, mainly by tracking the validation loss.
Dropout Layer 0.3: Added in front of dense layers to enhance generalization.
Data augmentation led to the dataset becoming more diverse and robust.

Model Evaluation and Results After training on Google Colab, the model gave a very fine classification performance.

**Metric	Training	Validation**

| Metric   | Training | Validation |
| -------- | -------- | ---------- |
| Accuracy | 95.7%    | 93.8%      |
| Loss     | 0.11     | 0.18       |
The confusion matrix and class-wise F1 scores showed that the model generalizes well on unseen data in terms of accuracy for all categories. 
Visualization: Training and Validation Accuracy Curves: The learning convergence was stable. Sample Predictions: Streamlit app shows uploaded images with predicted class labels and confidence scores.

**Deployment**
The model was utilized to develop a Streamlit web application capable of interacting in real time.
1. User uploads the image of waste.
2. Model predicts the category of waste with a confidence score.
3. Results are provided with a visual label and an optional bar chart.

Run Locally streamlit run app.py Run in Google Colab!streamlit run app.py & sleep 5 && cloudflared tunnel --url http://localhost:8501 --no-autoupdate

**Future Improvements **
Introduce e-waste, organic, and chemical categories for wastes. Integrating IoT based waste bins could manage deposition automatically. Deploy the model on Streamlit Cloud or Hugging Face Spaces. Perform low-light image detection to improve performance by data augmentation and image enhancement.
**Conclusion **
This work represents how Artificial Intelligence and Computer Vision can contribute to sustainable development through automating waste segregation. The utilization of transfer learning, data preprocessing, and deployment with Streamlit has generated a high-accuracy, lightweight, and easily scalable system-important for AI-powered environmental management and innovation in smart cities.

**Author**
Abhinav Chanakya
Candidate Registration Number: 1000308
IBCP Student – Meluha International School
Career-Related Study: Artificial Intelligence
Project Title: Smart Waste Classification System for Smart Cities


**Screenshots**
<img width="485" height="776" alt="image" src="https://github.com/user-attachments/assets/ca3392ac-b975-4c3c-b67e-eb248c0de71d" />
<img width="465" height="891" alt="image" src="https://github.com/user-attachments/assets/d724d49d-b3b9-47e5-893c-d9a351829279" />
<img width="475" height="812" alt="image" src="https://github.com/user-attachments/assets/371ff592-589e-4cfa-9674-767986b258f4" />
<img width="446" height="755" alt="image" src="https://github.com/user-attachments/assets/13548209-a17b-4ddc-b9cc-8f4db9956680" />
<img width="449" height="846" alt="image" src="https://github.com/user-attachments/assets/9be2d0a6-bc83-4883-abee-48f0537f72b5" />


