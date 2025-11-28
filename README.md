# Master Thesis – Surface Quality Prediction (XAI)

This repository contains the Python code and Jupyter notebooks for my master thesis  
**"Development of an Explainability Framework for Surface Quality Predictions Using Neural Networks"**.

The project is written in Python.  
All dependencies are listed in `requirements.txt`.  
The main content of this repository is a set of Jupyter notebooks.

---

## 1. Requirements

- Python 3.10+
- `git`
- A terminal:
  - Windows: PowerShell, CMD, or Git Bash
  - macOS / Linux: any shell
- Jupyter Lab or VS Code with Jupyter extension

---

## 2. Clone the repository

```bash
git clone https://github.com/LgendSourabie/explainable_ai.git
cd explainable_ai
```

# On Windows (PowerShell)

## create virtual environment in folder ".venv"

python -m venv .venv

## activate virtual environment

```
.\.venv\Scripts\Activate.ps1
```

# On macOS / Linux

## create virtual environment in folder ".venv"

```
python3 -m venv .venv

```

## activate virtual environment

```
source .venv/bin/activate

```

# Install dependencies

```
pip install --upgrade pip
pip install -r requirements.txt

```

# Notebooks overview

## data_preparation.ipynb

This notebook is used for data preparation.
Typical steps in this notebook are:

load the raw measurement data

clean the data (remove invalid rows, handle missing values, basic filtering)

## neural_network_training_paper_params.ipynb

Load the prepared train, validation and test data created in data_preparation.ipynb.

Define the neural network architecture (layers, activation functions, etc.).

Set the training parameters from the paper (learning rate, batch size, epochs, optimizer, loss function).

Train the model on the training data and monitor the performance on the validation data.

Evaluate the final model on the test set.

Save the trained model weights and, if needed, prediction results to disk.

Optionally create plots or logs of metrics (for example loss curves, error measures).

## explanability.ipynb

Load the trained neural network model from neural_network_training_paper_params.ipynb.

Load the test data or selected samples for explanation.

Build the explanation pipeline:

data input → model prediction → explanation method → visualization

Apply one or more XAI methods (for example: feature importance, sensitivity analysis, or other explainers).

Generate explanations for single predictions and/or for groups of samples.

Create plots or tables that show:

which features are important

how changes in inputs affect the prediction

Save the explanation results (figures, data files) for use in the thesis or later analysis.

Run this notebook after the model has been trained and saved.

## deviation_batch_top_10.ipynb

Load the trained neural network model from neural_network_training_paper_params.ipynb.

Load the test data or selected samples for explanation.

Build the explanation pipeline:
data input => model prediction => explanation method => visualization.

Apply one or more XAI methods (for example: feature importance, sensitivity analysis, or other explainers).

Generate explanations for single predictions and/or for groups of samples.

Create plots or tables that show:

which features are important,

how changes in inputs affect the prediction.

Save the explanation results (figures, data files) for use in the thesis or later analysis.

Run this notebook after the model has been trained and saved.

## post_explanation.ipynb

Load the model predictions, true values, and (if available) explanation results from previous notebooks.

Define one or more outlier criteria, for example:

very high prediction error,

unusual feature values,

unusual explanation patterns.

Detect outliers in the dataset based on these criteria.

Analyze the outliers in more detail:

inspect their input features,

inspect their explanations,

compare them to normal samples.

Create plots and tables that summarize:

which samples are outliers,

how they differ from the rest of the data.

Save the outlier lists, plots, and any derived statistics for use in the thesis.
