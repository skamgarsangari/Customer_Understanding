# Lead Prioritization Tool

## Project Overview
This tool analyzes customer lead data to prioritize sales calls and maximize signup potential. It processes three key datasets (leads, previous calls, and historical signups) to build a prediction model that identifies the most promising leads for future outreach.

## Features
- Data cleaning and preprocessing of customer lead information
- Analysis of historical call outcomes and signup rates
- Machine learning model to predict signup probability based on demographic and behavioral data
- Prioritized list generation of top leads to call for maximum conversion

## Data Structure
The project works with three primary datasets:
1. **Leads** (`leads.csv`):
   - Contains potential customer information with fields for Name, Phone Number, Region, Sector, and Age
   
2. **Calls** (`calls.csv`):
   - Records of previous call attempts with Phone Number, Call Outcome, Agent, and Call Number
   
3. **Signups** (`signups.csv`):
   - Records of which leads converted to signups and their approval decisions

## Workflow
1. Data loading and cleaning
2. Feature engineering from demographic data
3. Identification of contacted vs. uncontacted leads
4. Merge of lead and call history data
5. Analysis of last call per lead
6. Correlation with signup data
7. Machine learning model training using scikit-learn
8. Prediction of signup probability for uncontacted leads
9. Generation of top 1000 leads to call

## Dependencies
- Python 3.x
- pandas
- scikit-learn
- numpy
- Jupyter Notebook

## Installation
```bash
# Clone the repository
git clone https://github.com/yourusername/lead-prioritization-tool.git

# Navigate to the project directory
cd lead-prioritization-tool

# Install required packages
pip install -r requirements.txt
```

## Usage
1. Place your CSV data files in the project directory:
   - leads.csv
   - calls.csv
   - signups.csv

2. Run the Jupyter notebook:
```bash
jupyter notebook top1000_leads_tocall.ipynb
```

3. The notebook will process the data and output a prioritized list of leads to call

## Project Structure
```
lead-prioritization-tool/
├── README.md
├── requirements.txt
├── top1000_leads_tocall.ipynb
├── leads.csv
├── calls.csv
└── signups.csv
```

## Notes on Data Processing
- The code filters out leads with unrealistic age values (Age > 100)
- For contacted leads, it focuses on the most recent call outcome
- Feature encoding uses one-hot encoding for categorical variables (Region, Sector)
- The model is trained on a stratified split to handle potential class imbalance in signup data

## Future Improvements
- Add model evaluation metrics and performance tracking
- Implement feature importance analysis to better understand conversion factors
- Add a time-series component to account for seasonal trends
- Create a web interface for non-technical users

## License
[MIT](https://choosealicense.com/licenses/mit/)

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.