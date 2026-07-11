# Sentiment Analysis with TensorFlow and spaCy
![Python](https://img.shields.io/badge/Python-3.12-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Deep%20Learning-orange)
![spaCy](https://img.shields.io/badge/spaCy-NLP-green)
![License](https://img.shields.io/badge/License-MIT-lightgrey)
## Overview

This project is a sentiment analysis system that leverages deep learning techniques with TensorFlow and sentence vectorization using spaCy.
It is designed to classify Amazon reviews into three sentiment categories: **Positive, Neutral, and Negative**. 
The dataset used for training has been preprocessed to ensure balanced sentiment distribution, making the model more robust and accurate.

The goal of this project is to create a scalable and efficient sentiment analysis tool that can be used for customer feedback analysis, brand monitoring, and other applications that require automated sentiment classification.

This project is maintained by **Divyanshu Garg**

### Key Objectives:

- **Automate sentiment classification** for Amazon reviews.
- **Improve accuracy** using deep learning techniques.
- **Deploy a functional sentiment analysis model** for real-world usage.
- **Ensure a balanced dataset** to avoid model bias.
- **Provide an easy-to-use API** for sentiment classification.

## Features

- **Text Preprocessing**: Uses spaCy for tokenization and sentence vectorization.
- **Deep Learning Model**: A TensorFlow-based neural network trained for sentiment classification.
- **Balanced Dataset**: Preprocessing step ensures a more even distribution of sentiment classes.
- **Modular Codebase**: Includes separate scripts for training, testing, and deployment.
- **Pretrained Model**: A trained model (`modelv0.0.h5`) for immediate inference.

## Project Structure

```
├── data.ipynb          # Preprocessing the dataset
├── model_main.ipynb    # Training the sentiment analysis model
├── test.ipynb          # Evaluating the trained model
├── server/             # Deployment-related files
│   ├── manage.py       # Entry point for running the application
│   ├── modelv0.0.h5    # Pretrained sentiment analysis model
```

## Dataset

You can download the dataset from the following link:
[Amazon Product Reviews Dataset](https://www.kaggle.com/datasets/arhamrumi/amazon-product-reviews?select=Reviews.csv)

## Installation & Setup

To set up the environment, follow these steps:

1. Clone the repository:

   ```sh
   git clone https://github.com/divyanshu-0508/Sentiment-Analyzer.git
   cd sentiment-analysis
   ```

2. Ensure you have Python 3.8+ and install the required packages:

   ```sh
   pip install tensorflow spacy numpy pandas scikit-learn streamlit
   ```

3. Download the spacy pretrained model
   ```sh
   python -m spacy download en_core_web_lg
   ```
4. Run the dataset preprocessing script (`data.ipynb`) to prepare the training data.

5. Train the model using:

   ```sh
   jupyter notebook model_main.ipynb
   ```

6. Test the trained model with:

   ```sh
   jupyter notebook test.ipynb
   ```

7. Run the application using `manage.py`:

   ```sh
   cd server
   python manage.py runserver
   ```

### Running the Project Directly

After installing the necessary dependencies, you can directly run the project using `manage.py` in the `server/` directory. This will start the API server, allowing you to send requests and receive sentiment predictions.

```sh
cd server
python streamlit run manage.py 
```

This approach is useful if you want to use the trained model for inference without retraining.

## Model Details

The sentiment analysis model is a deep neural network with the following architecture:

- **Input**: Sentence vectors from spaCy
- **Hidden Layers**: Fully connected layers with ReLU activation, batch normalization, and dropout for regularization
- **Output Layer**: Softmax activation for three sentiment classes
- **Loss Function**: Sparse categorical cross-entropy
- **Optimizer**: Adam with a learning rate of 0.0005

## How the Code Works

1. **Data Preprocessing (****`data.ipynb`****)**:

   - Loads raw Amazon reviews.
   - Cleans the text (removes special characters, lowercasing, etc.).
   - Converts text into sentence vectors using spaCy.
   - Balances the dataset for better training performance.

2. **Model Training (****`model_main.ipynb`****)**:

   - Defines and compiles a deep learning model using TensorFlow.
   - Trains the model on processed review vectors.
   - Saves the trained model as `modelv0.0.h5` in the `server` directory.

3. **Model Testing (****`test.ipynb`****)**:

   - Loads the trained model.
   - Evaluates accuracy on test data.
   - Generates sentiment predictions.

4. **Deployment (****`server/manage.py`****)**:

   - Runs a simple API server to serve predictions.
   - Takes input reviews and returns sentiment classifications.

## Contributing

Contributions, feature requests, and bug reports are welcome. Feel free to open an issue or submit a pull request.

## Developer
- **Divyanshu Garg** - https://github.com/divyanshu-0508
