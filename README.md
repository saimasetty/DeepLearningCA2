Plant Disease Detection Using CNN


A Deep Learning image-classification project that uses a Convolutional Neural Network (CNN) built from scratch with TensorFlow/Keras to classify tomato leaf images into four supported categories.
Project Overview
The notebook downloads the PlantVillage dataset through TensorFlow Datasets, selects four tomato leaf classes, prepares training/validation/test splits, trains a CNN, evaluates its predictions, and lets users test their own leaf images.
Supported classes
- Tomato healthy
- Tomato early blight
- Tomato late blight
- Tomato leaf mold
The notebook checks the available dataset labels and maps them to these categories.
Technology Stack
- Python
- Google Colab
- TensorFlow / Keras
- TensorFlow Datasets
- NumPy and Pandas
- Matplotlib and Seaborn
- scikit-learn
- Pillow
Dataset
The project uses the PlantVillage dataset via TensorFlow Datasets (plant_village).

Dataset information:
- TensorFlow Datasets catalog: https://www.tensorflow.org/datasets/catalog/plant_village
- PlantVillage dataset repository: https://github.com/spMohanty/PlantVillage-Dataset
The notebook filters the dataset to the four tomato classes listed above. The actual number of images depends on the dataset version and the classes available at runtime.
How to Run
1. Open the Plant_Disease_Detection.ipynb notebook in Google Colab.
2. Select Runtime → Run all (or run cells in order).
3. Allow the notebook to install any required dependency and download the dataset.
4. Wait for dataset preparation and model training to finish.
5. Review the training graphs and test-set evaluation.
6. Run the final image-upload cell to test the model with a JPG, JPEG, or PNG leaf image.
A GPU runtime can speed up training. To enable one, select Runtime → Change runtime type → T4 GPU (if available).
Model Architecture
The notebook builds a CNN from scratch using Keras. The architecture includes:
- Convolutional layers with ReLU activation
- Batch normalization
- Max pooling
- Dense classification layers
- A softmax output layer
Images are resized to 128 × 128 pixels and normalized to the range [0, 1]. Training augmentation includes modest rotations, shifts, zoom, and horizontal flipping.

Training uses Adam, sparse categorical cross-entropy, early stopping, and model checkpointing. The notebook uses a nominal 70% / 15% / 15% training, validation, and test split.
Evaluation and Outputs
The notebook generates:
- Training and validation accuracy graph (accuracy_graph.png)
- Training and validation loss graph (loss_graph.png)
- Test-set accuracy and loss
- Classification report (classification_report.csv)
- Confusion matrix (confusion_matrix.png)
- Sample predictions on held-out test images
- Predictions for user-uploaded images
Metrics are produced when the notebook is executed. No performance value is stated here because results depend on the actual training run.
Generated Model and Deliverables
After a successful run, the notebook saves the best model checkpoint as:
- best_plant_disease_model.keras
It also creates class mapping and evaluation artifacts, then packages the model and results into a ZIP archive for download.

Generated files are created in the Colab runtime. Download them before the runtime is deleted if you want to keep them.
Limitations
- The model only predicts among the classes it was trained on.
- PlantVillage images may differ from photographs taken outdoors, so real-world predictions can be less reliable.
- A model confidence score is not a guarantee that a prediction is correct.
- This project is an educational image classifier, not a definitive plant disease diagnosis tool.
Repository Contents
- Plant_Disease_Detection.ipynb — main notebook containing dataset preparation, CNN training, evaluation, and prediction workflow.
- README.md — project documentation.
License and Dataset Attribution
Check the PlantVillage dataset's source repository and applicable dataset terms before redistributing dataset images. This repository's code and the dataset may have different licensing terms.# DeepLearningCA2
