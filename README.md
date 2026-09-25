
# Business Entity Resolution

A machine learning-based system for matching business entities across multiple data sources. The project identifies potential matches between records from Source 1 and records from Source 2 and Source 3 using data normalization, similarity-based feature engineering, and a gradient boosting classification model.

## Project Overview

Business Entity Resolution is the process of identifying records from different data sources that refer to the same real-world business entity.

This project processes business records and generates:

- Final entity matches
- Candidate entity pairs used for matching
- Structured output files for evaluation

The system is designed to handle variations in business names, addresses, and other entity attributes.

## Features

- Text normalization for business records
- Similarity-based feature engineering
- Candidate generation using exact normalized fields
- Machine learning-based pair classification
- Hard negative sampling for improved training
- Threshold-based match prediction
- Candidate and final matching output generation

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- RapidFuzz
- Jupyter Notebook
- Machine Learning
- Gradient Boosting

## Project Structure

```text
business-entity-resolution/
│
├── Business_Entity_Resolution_CLEAN.ipynb
│
├── output/
│   ├── matching_results.tsv
│   └── candidate_pairs.tsv
│
└── README.md
```

## Methodology

### 1. Data Preparation

Business records are loaded from multiple data sources. Relevant fields are processed and prepared for matching.

### 2. Text Normalization

Text normalization is applied to reduce differences caused by:

- Case variations
- Unicode formatting
- Punctuation
- Whitespace
- Text representation

### 3. Feature Engineering

Similarity features are created from business attributes, including:

- Business name similarity
- Address similarity
- Other matching-related attributes

RapidFuzz similarity metrics are used to calculate text similarity scores.

### 4. Candidate Generation

Candidate records are generated using normalized fields such as business names and addresses.

This reduces the number of record pairs that need to be evaluated by the machine learning model.

### 5. Machine Learning Model

A `HistGradientBoostingClassifier` is trained to classify record pairs as:

- Match
- Non-match

The training process includes positive examples, random negative examples, and hard negative examples.

### 6. Prediction

The trained model predicts matching probabilities for candidate pairs. A classification threshold is applied to generate the final entity matches.

## Output Files

### `output/matching_results.tsv`

Contains the final predicted matches for each Source 1 entity.

| Column | Description |
|---|---|
| `source1_entity_id` | ID of the Source 1 entity |
| `matched_entity_ids` | Matching entity IDs from Source 2 and Source 3 |

### `output/candidate_pairs.tsv`

Contains the candidate entity IDs considered during the matching process.

| Column | Description |
|---|---|
| `source1_entity_id` | ID of the Source 1 entity |
| `candidate_entity_ids` | Candidate entity IDs evaluated for matching |

## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/business-entity-resolution.git
cd business-entity-resolution
```

### 2. Install Dependencies

Install the required Python libraries:

```bash
pip install pandas numpy scikit-learn rapidfuzz jupyter
```

### 3. Prepare the Dataset

Place the provided dataset archive in the project directory:

```text
student_resource.zip
```

The dataset is not included in this repository.

### 4. Run the Notebook

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
Business_Entity_Resolution_CLEAN.ipynb
```

Run the notebook cells in order to train the model and generate the output files.

## Results

The pipeline generates matching results and candidate pairs for the Source 1 test entities.

The generated files are saved in the `output/` directory.

> Note: The final performance depends on the evaluation dataset and official validation process.

## Disclaimer

This repository contains the implementation and generated outputs for the Business Entity Resolution project. The dataset is excluded from the repository because of its size and data distribution requirements.

## Author

**YOUR_NAME**

GitHub: https://github.com/YOUR_USERNAME
