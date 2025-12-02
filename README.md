# DSAN6650 Final Project - Reinforcement Learning for Recommendation Systems

## 📋 Project Overview
This project implements and compares different bandit algorithms for online advertising recommendation, including:
- Neural UCB
- Linear UCB (LinUCB)
- Random baseline

## 🗂️ Project Structure
```
.
├── DSAN6650_final_Eng.ipynb    # Main notebook with all experiments
├── train.gz                     # CTR prediction dataset
├── requirements.txt             # Python dependencies
└── README.md                    # This file
```

## 📊 Dataset
The project uses the Avazu Click-Through Rate Prediction dataset:
- **Source**: Kaggle Avazu CTR Prediction Competition
- **File**: `train.gz` (compressed CSV file)
- **Size**: First 1,000,000 rows used for experiments
- **Features**: 24 features including user, ad, and context information
- **Target**: Binary click/no-click labels

### Data Download
If `train.gz` is not included in this repository, you can download it from:
- [Kaggle Avazu CTR Dataset](https://www.kaggle.com/c/avazu-ctr-prediction/data)
- Place the downloaded `train.gz` file in the project root directory

## 🔧 Setup Instructions

### Prerequisites
- Python 3.9+
- Jupyter Notebook or Google Colab

### Installation
1. Clone this repository:
```bash
git https://github.com/HongzheWang0922/DSAN6650_Team03_FInal
cd DSAN6650_Team03_FInal
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Download the dataset (if not included):
   - Download `train.gz` from Kaggle
   - Place it in the project root directory

### Running the Notebook

**Option 1: Local Jupyter**
```bash
jupyter notebook DSAN6650_Final.ipynb
```

**Option 2: Google Colab**
1. Upload the notebook to Google Colab
2. Upload `train.gz` to your Google Drive
3. Update the data path in the notebook (line 137):
```python
data_path = '/content/drive/MyDrive/YOUR_PATH/train.gz'
```
4. Run all cells

## 🧪 Experiments

### Bandit Algorithms Evaluated
1. **Neural UCB**: Neural network-based contextual bandit with upper confidence bound
2. **LinUCB**: Linear contextual bandit with upper confidence bound
3. **Random Baseline**: Random action selection

### Key Metrics
- **Match Rate**: Percentage of correct action selections
- **Total Reward**: Cumulative rewards obtained
- **Expected CTR**: Predicted click-through rate
- **Action Diversity**: Entropy of action distribution

### Experiment Settings
- Total rounds: 10,000
- Candidate set: Top-200 most frequent actions
- Features: 7 contextual features (C14, C15, C16, C17, C18, C19, C21)

## 📈 Results Summary
The notebook includes comprehensive visualizations and analysis:
- Cumulative reward curves
- Match rate evolution
- Action distribution analysis
- Algorithm comparison metrics

## 🛠️ Technical Details

### Key Components
- **Feature Engineering**: Categorical encoding and normalization
- **Neural Network**: 2-layer MLP for Neural UCB
- **Exploration-Exploitation**: UCB-based action selection
- **Evaluation**: Both online learning metrics and offline CTR prediction

### Dependencies
- numpy: Numerical computing
- pandas: Data manipulation
- matplotlib/seaborn: Visualization
- scipy: Statistical functions

## 📝 Notes
- The notebook is designed to run in Google Colab with GPU acceleration
- For local execution, remove Google Drive mounting code (cells 1)
- Kaggle API credentials are required for direct dataset download


