# README.md

## Installation

To set up the environment, install the required dependencies using the provided `requirements.yml` file:

```bash
conda env create -f NEST_environment.yml
conda activate NEST_train
```

## File Dependencies

Ensure that the training and testing raw data files are present in the appropriate directories before proceeding.
Download the `TESTWITHSTUDY.xlsx`, `usecase_3_.csv` from the google drive link provided and place it in the root directory before running the code. 
`https://drive.google.com/drive/folders/13hQ9FHH83WCx83eBLoGyDlAk1OuaqMnG?usp=sharing`

## Execution Steps

### 1. **Run LLM Training and Testing Notebooks**

- **LLM\_train.ipynb**:
  - Loads the dataset and preprocesses the textual information.
  - Utilizes Hugging Face `transformers` to classify text using zero-shot classification.
  - Saves processed outputs for downstream tasks.
- **LLM\_test.ipynb**:
  - Loads the trained model from the training notebook.
  - Runs predictions on test data.
  - Evaluates model performance.
- **Note:** Before running these notebooks, update the `folder_path` variable accordingly. The `folder_path` needs to be updated for every file.

### 2. **Run ClinicalBioBert Fine-Tuning Notebook**

- **ClinicalBioBert\_Fine\_Tuning.ipynb**:
  - Fine-tunes BioBERT for clinical text classification.
  - Uses `Hugging Face` Trainer API for efficient model training.
  - Generates embeddings for medical trial descriptions.

### 3. **Run Data Preprocessing Notebooks**

- **Data\_Preprocessing\_train.ipynb**:
  - Reads and cleans training dataset.
  - Handles missing values and performs feature engineering.
  - Encodes categorical variables and normalizes numerical features.
- **Data\_Preprocessing\_test.ipynb**:
  - Applies the same transformations as `Data_Preprocessing_train.ipynb` to test data.
  - Ensures consistency in data format and feature distribution.

### 4. **Run XGBoost Model Notebook**

- **XGBoost.ipynb**:
  - Loads preprocessed training data.
  - Trains an `XGBoost` classifier for trial completion prediction.
  - Evaluates model performance using classification metrics like precision, recall, and F1-score.

### 5. **Run Ensemble Bagging Notebook**

- **Ensembele\_bagging.ipynb**:
  - Implements an ensemble bagging strategy to improve predictive accuracy.
  - Combines multiple weak learners to reduce variance and increase robustness.
  - Evaluates final model performance and compares it with standalone `XGBoost` results.

## Output

- The final results, including the test metrics, will be displayed in the `Ensembele_bagging.ipynb` notebook.
- These include accuracy, precision, recall, and F1-score, providing insights into model performance.

Ensure that all dependencies are correctly installed and all required files are present before execution.
  --- 