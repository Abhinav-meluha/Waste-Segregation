# Waste-Management

**Overview**

The Smart Waste Classification System is a computer vision project designed to automatically classify waste into categories such as Biodegradable, Recyclable, and Hazardous using Deep Learning.
The system employs Transfer Learning with the MobileNetV2 architecture to achieve high accuracy while maintaining computational efficiency.
It is deployed via a Streamlit web interface, enabling real-time waste recognition for smart city waste management.

**Research Background and Findings**

The growing issue of improper waste segregation has a major impact on environmental sustainability and urban sanitation.
Research studies have shown that Artificial Intelligence (AI) can significantly enhance waste sorting accuracy and efficiency in recycling systems.

Key Research Findings Influencing This Project:
**Automation in Waste Management**: Studies indicate that AI and deep learning models outperform traditional manual sorting systems by reducing classification errors and improving sorting speed.
**Transfer Learning Efficiency:** Academic literature demonstrates that transfer learning with models like MobileNetV2 or ResNet50 is effective for environmental datasets with limited images, reducing the need for large-scale retraining.
**Sustainability Impact:** Intelligent waste classification systems are directly aligned with UN Sustainable Development Goals (SDG 11 – Sustainable Cities and Communities) by promoting eco-friendly waste disposal and recycling.

**Dataset Preparation**

Data Collection and Structure
The dataset consists of images categorized into 10 waste types:
battery, biological, cardboard, clothes, glass, metal, paper, plastic, shoes, trash
Each class contains hundreds of labeled images representing real-world waste materials.

Data Preprocessing Steps:

1. Data Cleaning: Removed corrupted or unreadable image files.
2. Data Splitting: Divided the dataset into:
70% Training
20% Validation
10% Testing
3. Image Augmentation: Applied random transformations such as:
Rotation (±15°)
Zoom (0.2)
Horizontal flip
Rescaling (1/255 normalization)
4. Image Resizing: Standardized all images to 224×224 pixels for MobileNetV2 input compatibility.

**Model Design and Training**

Model Used:
Architecture: MobileNetV2
Framework: TensorFlow / Keras
Transfer Learning: Pretrained on ImageNet, fine-tuned on waste dataset

Training Parameters:
| Parameter     | Value                                                 |
| ------------- | ----------------------------------------------------- |
| Optimizer     | Adam                                                  |
| Learning Rate | 0.001 (auto reduced to 0.0003 with ReduceLROnPlateau) |
| Loss Function | Categorical Crossentropy                              |
| Batch Size    | 32                                                    |
| Epochs        | 10                                                    |
| Metrics       | Accuracy                                              |

Regularization Techniques:
EarlyStopping: Prevented overfitting by monitoring validation loss.
Dropout Layer (0.3): Added before dense layers to improve generalization.
Data Augmentation: Increased dataset diversity and robustness.

**Model Evaluation and Results**
After training on Google Colab, the model achieved strong classification performance:
| Metric   | Training | Validation |
| -------- | -------- | ---------- |
| Accuracy | 95.7%    | 93.8%      |
| Loss     | 0.11     | 0.18       |

The confusion matrix and class-wise F1 scores indicated consistent accuracy across all categories, demonstrating that the model can generalize well on unseen data.

Visualization:
Training and Validation Accuracy Curves: Showed stable learning convergence.
Sample Predictions: Streamlit app displayed uploaded images with predicted class labels and confidence scores.

**Deployment**
The trained model was integrated into a Streamlit web application, allowing real-time interaction:

1. User uploads a waste image.
2. The model predicts the waste category with a confidence score.
3. Results are displayed with a visual label and optional bar chart.

Run Locally
streamlit run app.py

Run in Google Colab
!streamlit run app.py & sleep 5 && cloudflared tunnel --[url http://localhost:8501](https://self-keeping-targeted-lauren.trycloudflare.com/) --no-autoupdate

Future Enhancements

Add new waste categories (e-waste, organic, chemical).
Integrate IoT-based smart bins for automated disposal.
Deploy on Streamlit Cloud or Hugging Face Spaces for public access.
Improve low-light image detection using data augmentation and image enhancement.

**Conclusion**
This project demonstrates how Artificial Intelligence and Computer Vision can support sustainable development by automating waste segregation.
By applying transfer learning, data preprocessing, and deployment via Streamlit, the system achieves high accuracy while remaining lightweight and scalable.
It is a significant step toward AI-driven environmental management and smart city innovation.

**Author**
Abhinav Chanakya
IBCP Student – Meluha International School
Career-Related Study: Artificial Intelligence
Project Title: Smart Waste Classification System for Smart Cities
