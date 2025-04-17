# 📞 Prioritization of Calls

## 🧠 Project Overview

This tool analyzes customer lead data to prioritize sales calls and **maximize signup potential**. It integrates and processes three key datasets—leads, previous calls, and historical signups—to build a machine learning model that identifies the most promising leads for outreach.

## ✨ Features

- Preprocessing and cleaning of customer lead data
- Analysis of historical call outcomes and signup rates
- Machine learning model to predict signup probability using demographic and behavioral features
- Automatic generation of a prioritized lead list for maximum conversion potential

## 🗂️ Data Structure

This project works with three primary datasets:

1. **Leads** (`leads.csv`)
   - Fields: `Name`, `Phone Number`, `Region`, `Sector`, `Age`

2. **Calls** (`calls.csv`)
   - Fields: `Phone Number`, `Call Outcome`, `Agent`, `Call Number`

3. **Signups** (`signups.csv`)
   - Fields: `Phone Number`, `Signup Status`, `Approval Decision`

## 🔁 Workflow

1. Load and clean input datasets
2. Engineer features from demographic and behavioral data
3. Identify contacted vs. uncontacted leads
4. Merge lead and call history data
5. Analyze last call outcome per lead
6. Join with signup data
7. Train predictive model using scikit-learn
8. Predict signup probability for uncontacted leads
9. Output the top 1,000 leads to call next

## 📦 Dependencies

- Python 3.x
- `pandas`
- `numpy`
- `scikit-learn`
- `Jupyter Notebook`

## ⚙️ Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/lead-prioritization-tool.git

# Navigate into the project directory
cd lead-prioritization-tool

# Install the required dependencies
pip install -r requirements.txt
```

## ▶️ Usage

1. Add your data files to the project directory:
   - `leads.csv`
   - `calls.csv`
   - `signups.csv`

2. Launch the Jupyter notebook:
   ```bash
   jupyter notebook top1000_leads_tocall.ipynb
   ```

3. Run the notebook to process the data and generate the prioritized list of leads to call.

## 📁 Project Structure

```
lead-prioritization-tool/
├── README.md
├── requirements.txt
├── top1000_leads_tocall.ipynb
├── leads.csv
├── calls.csv
└── signups.csv
```

## 📝 Notes on Data Processing

- Filters out unrealistic entries (e.g., `Age > 100`)
- For contacted leads, only the **most recent call** is used
- Categorical features (e.g., `Region`, `Sector`) are encoded using one-hot encoding
- Stratified train-test split is used to handle potential class imbalance

## 🚀 Future Improvements

- Add evaluation metrics (AUC, precision-recall, etc.)
- Analyze feature importance to understand key conversion drivers
- Incorporate time-series trends for seasonal modeling
- Build a simple web interface for non-technical users

## 🪪 License

[MIT License](https://choosealicense.com/licenses/mit/)

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.
