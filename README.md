
# Automating ROP Diagnosis and Severity with Deep Learning

## Project Overview

Retinopathy of Prematurity (ROP) is a condition affecting premature infants, which can lead to blindness if not detected and treated early. Due to the global shortage of trained specialists, particularly in resource-limited settings, timely diagnosis of ROP is challenging. This project aims to bridge this gap by leveraging deep learning to classify the severity of ROP from retinal images, enabling automated and scalable diagnosis.

This study compares the performance of five deep learning architectures: 
- Custom Convolutional Neural Network (CNN)
- ResNet
- EfficientNet
- Inception
- VGG

The **Custom CNN** model outperformed others with a test accuracy of **98.48%**, making it the most reliable choice for automated ROP screening.

---

## Features
- **Classification of ROP Severity**: Automatic classification into 10 diagnostic classes using retinal fundus images.
- **Custom Deep Learning Model**: A CNN architecture specifically optimized for ROP detection.
- **Data Augmentation**: Addressing class imbalance through transformations to improve model generalization.
- **Comparative Analysis**: Evaluation of popular architectures like ResNet, EfficientNet, and Inception against the custom CNN.

---

## Dataset

The dataset is sourced from Kaggle, containing **6,004 retinal images** collected during ROP screenings at University Hospital Ostrava, Czech Republic. The images were annotated with:
- Diagnosis Codes (11 classes, reduced to 10 post-augmentation)
- Patient Metadata: Sex, Gestational Age, Birth Weight, Postconceptual Age, Imaging Device, and Series Number.

### Data Augmentation
To improve class balance and model robustness, the dataset was augmented using transformations:
- Small random rotations (up to 2°)
- Shifts (up to 5% of image dimensions)
- Scaling variations (0.85 to 1.15)
- Horizontal flips

Post-augmentation, the dataset grew to **12,342 images**, representing 10 diagnostic classes.

---

## Model Architectures

### 1. **Custom CNN**
- Achieved the highest test accuracy of **98.48%** and test loss of **0.06**.
- Strong performance on most diagnostic classes, especially DG0 (No ROP).

### 2. **ResNet**
- Accuracy: **95.35%**, Test Loss: **0.14**
- Effective in extracting deep features with residual connections.

### 3. **EfficientNet**
- Accuracy: **96.07%**, Test Loss: **0.13**
- Utilized MBConv blocks for efficient feature extraction.

### 4. **Inception**
- Accuracy: **91.83%**, Test Loss: **0.25**
- Parallel convolutional paths for complex feature representation.

### 5. **VGG**
- Accuracy: **88.86%**, Test Loss: **0.32**
- Simplified architecture but showed limited performance.

---

## Results

| Model        | Test Accuracy | Test Loss |
|--------------|---------------|-----------|
| Custom CNN   | 98.48%        | 0.06      |
| EfficientNet | 96.07%        | 0.13      |
| ResNet       | 95.35%        | 0.14      |
| Inception    | 91.83%        | 0.25      |
| VGG          | 88.86%        | 0.32      |

**Confusion matrices** and training/validation accuracy plots are included in the results for a detailed analysis.

---

## Installation

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/username/rop-diagnosis.git
   cd rop-diagnosis
   ```

2. **Install Dependencies**  
   Ensure you have Python 3.8 or higher installed. Install the required Python packages by running:  
   ```bash
   pip install tensorflow keras matplotlib scikit-learn
   ```

3. **Additional Dependencies**  
   If data augmentation is required, install the following:  
   ```bash
   pip install pillow
   ```

4. **Dataset Setup**  
   - Download the dataset from [Kaggle](https://www.kaggle.com/datasets/jananowakova/retinal-image-dataset-of-infants-and-rop/data).  
   - Place the dataset in the `data/` directory or the path specified in the notebook.

---

## Usage

1. **Run Data Augmentation (Optional)**  
   To generate augmented data for imbalanced classes, execute the augmentation code in the notebook:
   - Modify `dataset_path` and `augmented_path` in the script.
   - Run the cell to create augmented images.

2. **Train the Model**  
   - Execute the training cells in the notebook.
   - Models implemented include CNN, ResNet, EfficientNet, and more.
   - Modify hyperparameters such as epochs, batch size, or model type as needed.

3. **Evaluate the Model**  
   - Run the evaluation cells to compute test accuracy and loss.
   - Results include confusion matrices and performance plots.

4. **Save the Model**  
   - Save the trained model using:  
     ```python
     model.save('model_name.h5')
     ```
   - Training history can also be saved as a JSON file.

5. **Visualize Results**  
   - Use the included scripts to plot training/validation accuracy and loss.
   - Generate and display confusion matrices.

---

## Future Work

- **Data Diversity**: Incorporate larger and more diverse datasets to improve generalization.
- **Explainable AI**: Enhance transparency using interpretable models.
- **Clinical Integration**: Deploy the model in Clinical Decision Support Systems (CDSS) for real-world applications.
- **Ensemble Models**: Combine strengths of multiple architectures to boost performance.

---

## Contributing

Contributions are welcome! Please follow these steps:
1. Fork this repository.
2. Create a new branch for your feature/bugfix.
3. Submit a pull request detailing the changes.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Authors

- **Ahsan Siddiqui** - [GitHub](https://github.com/ahsan-sidd)
- **Muhammad Mansoor Alam**
- **Zohaib Aslam**

For any inquiries, please contact us at:
- **Ahsan Siddiqui**: as08155@st.habib.edu.pk
