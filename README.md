# Mango Leaf Disease Classification

A deep learning-based system for automated detection and classification of mango leaf diseases using computer vision and neural networks.

## 📋 Overview

This project implements a machine learning solution for identifying diseases in mango leaves from images. Early detection of plant diseases is crucial for agricultural productivity and economic sustainability. This system enables farmers and agricultural experts to quickly diagnose mango leaf diseases, facilitating timely intervention and treatment.

## 🎯 Objective

The primary goal is to develop an accurate and efficient model that can classify mango leaves into different disease categories or identify them as healthy, supporting smart agriculture and precision farming initiatives.

## 🌿 Disease Categories

The model is trained to identify common mango leaf diseases, which may include:

- **Anthracnose**: Black necrotic patches on leaves
- **Powdery Mildew**: White powdery coating on leaf surfaces
- **Bacterial Canker**: Water-soaked spots and cankers
- **Sooty Mold**: Black fungal growth on leaves
- **Gall Midge**: Deformed leaf growth
- **Cutting Weevil**: Scissor-like cuts on leaves
- **Dieback**: Browning and drying of leaves
- **Healthy**: Normal, disease-free leaves

## 📁 Project Structure

```
Mango-Leaf-Diesease-Classification/
├── APIs/                   # API implementations for model serving
├── Notebooks/              # Jupyter notebooks for training and analysis
├── Results/                # Model outputs, metrics, and visualizations
└── README.md              # Project documentation
```

## 🛠️ Technologies Used

- **Deep Learning Frameworks**: TensorFlow/Keras or PyTorch
- **Computer Vision**: OpenCV, PIL
- **Data Processing**: NumPy, Pandas
- **Visualization**: Matplotlib, Seaborn
- **Model Deployment**: Flask/FastAPI (for APIs)
- **Development Environment**: Jupyter Notebook

## 🚀 Getting Started

### Prerequisites

```bash
Python 3.8+
pip or conda package manager
```

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Muhammad-Hassan-Farid/Mango-Leaf-Diesease-Classification.git
cd Mango-Leaf-Diesease-Classification
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

### Dataset

The project uses mango leaf image datasets that can be obtained from:
- Kaggle datasets
- MangoLeafBD or similar public repositories
- Custom collected data from mango orchards

Ensure your dataset is organized in the following structure:
```
data/
├── train/
│   ├── anthracnose/
│   ├── healthy/
│   └── [other disease classes]/
└── test/
    ├── anthracnose/
    ├── healthy/
    └── [other disease classes]/
```

## 📓 Usage

### Training the Model

Navigate to the `Notebooks/` directory and open the training notebook:

```bash
jupyter notebook Notebooks/training_notebook.ipynb
```

Follow the steps in the notebook to:
1. Load and preprocess the dataset
2. Configure model architecture
3. Train the model
4. Evaluate performance
5. Save the trained model

### Using the API

Start the API server from the `APIs/` directory:

```bash
python app.py
```

Make predictions via API endpoint:

```python
import requests

url = "http://localhost:5000/predict"
files = {"file": open("path/to/leaf_image.jpg", "rb")}
response = requests.post(url, files=files)
print(response.json())
```

### Making Predictions

For batch predictions or testing:

```python
from model import predict_disease

image_path = "path/to/mango_leaf.jpg"
prediction = predict_disease(image_path)
print(f"Predicted Disease: {prediction}")
```

## 📊 Model Architecture

The model likely employs one or more of the following approaches:

- **Convolutional Neural Networks (CNN)**: Custom architecture or pretrained models
- **Transfer Learning**: Using models like VGG16, ResNet, MobileNet, or EfficientNet
- **Data Augmentation**: To improve model robustness and generalization
- **Fine-tuning**: Adapting pretrained models to the specific task

## 📈 Results

Model performance metrics are available in the `Results/` directory, including:

- Accuracy scores
- Confusion matrices
- Precision, Recall, and F1-scores per class
- Loss and accuracy curves
- Sample predictions with visualizations

## 🔬 Model Evaluation

Key metrics for model assessment:

- **Training Accuracy**: Model performance on training data
- **Validation Accuracy**: Performance on unseen validation data
- **Test Accuracy**: Final performance on test set
- **Classification Report**: Detailed per-class metrics
- **ROC Curves**: True Positive vs False Positive rates

## 🌐 API Documentation

### Endpoints

#### POST `/predict`
Predicts the disease class for an uploaded mango leaf image.

**Request:**
- Method: POST
- Content-Type: multipart/form-data
- Body: image file

**Response:**
```json
{
  "prediction": "Anthracnose",
  "confidence": 0.95,
  "all_probabilities": {
    "Anthracnose": 0.95,
    "Healthy": 0.03,
    "Powdery Mildew": 0.02
  }
}
```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 Future Improvements

- [ ] Expand dataset with more disease categories
- [ ] Implement real-time detection via mobile app
- [ ] Add multi-language support for wider accessibility
- [ ] Integrate disease treatment recommendations
- [ ] Deploy as a web application
- [ ] Implement model quantization for edge deployment
- [ ] Add explainability features (Grad-CAM visualization)

## 🐛 Known Issues

- Model performance may vary with different lighting conditions
- Requires high-quality images for accurate predictions
- May struggle with images containing multiple diseases

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👤 Author

**Muhammad Hassan Farid**

- GitHub: [@Muhammad-Hassan-Farid](https://github.com/Muhammad-Hassan-Farid)

## 🙏 Acknowledgments

- Agricultural experts who provided domain knowledge
- Open-source dataset contributors
- The machine learning and computer vision community
- Research papers on mango leaf disease detection

## 📚 References

1. MangoLeafBD Dataset - Comprehensive mango leaf disease dataset
2. Deep Learning for Plant Disease Detection - Research papers and implementations
3. Transfer Learning in Agriculture - Best practices and methodologies

## 📞 Contact

For questions, suggestions, or collaboration opportunities, please:
- Open an issue in this repository
- Contact via GitHub profile

---

**Note**: This project is for educational and research purposes. Always consult with agricultural experts for professional plant disease diagnosis and treatment recommendations.
