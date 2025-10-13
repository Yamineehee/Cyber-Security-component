Malware Analysis Project - Demonstration Guide


Project ID: 35


Team: Swarnima Singh, Tijil Parakh, Vrushant Mukherjee, Yaminee Chaudhary
Mentors: Dr. Pooja Bagane, Dr. Sonali Kothari

Project Overview
A malware analysis system that uses sandbox environments and machine learning to detect malicious software with 100% accuracy.
Key Results:

100% detection accuracy
0% false positives
94% success against malware evasion techniques


Part 1: ANY.RUN Demonstration
ANY.RUN is an online malware analysis platform that shows real-time malware behavior.
Steps to Demonstrate:
1. Access Platform

Go to https://any.run
Login to your account
Click "New Task" button

2. Upload Sample

Click "Browse" and select malware sample
Choose Windows 10 as OS
Set timeout to 120 seconds
Click "Run"

3. Watch Analysis
Monitor these panels:

Process Tree - See what programs the malware launches
Network Activity - See what websites/IPs it contacts
File Changes - See what files it creates/deletes
Registry Changes - See persistence mechanisms

4. Review Results

Check malware family classification
Note behavioral indicators detected
Review threat level assessment

5. Export Data

Click "Export"
Download JSON report for machine learning
Download IoCs for blocking

What to Show:

How malware creates processes
Network connections to C2 servers
Files dropped on system
Registry keys modified for persistence
Overall threat assessment


Part 2: Python Code Implementation
Setup Instructions
Step 1: Install Python

Download Python 3.8 or higher
Install on your system

Step 2: Install Libraries
Open command prompt and run:
pip install numpy pandas scikit-learn tensorflow matplotlib seaborn
Step 3: Prepare Project Folders
Create these folders:

data (put your CSV files here)
models (trained models saved here)
scripts (put Python files here)
outputs (results saved here)

Running the Code
Step 1: Extract Features

Put sandbox reports in data folder
Run: feature_extraction.py
This creates a CSV with 14 behavioral features

Step 2: Train Models

Run: train_models.py
Trains 4 models: Random Forest, SVM, Gradient Boosting, Neural Network
Takes about 30-60 seconds
Models saved automatically

Step 3: Classify Samples

Run: classify_sample.py
Shows prediction for each model
Shows final ensemble decision (Malicious or Benign)
Shows confidence percentage

Step 4: Evaluate Performance

Run: evaluate_performance.py
Shows accuracy metrics
Displays confusion matrix
Shows 100% accuracy result

Step 5: Generate YARA Rules

Run: generate_threat_intel.py
Creates YARA detection rules
Extracts IoCs (IPs, domains, file hashes)
Saves rules to outputs folder

Expected Outputs
Feature Extraction:

Message: "Extracted features from 200 samples"
Creates: extracted_features.csv

Model Training:

Shows training progress for each model
Final message: "Ensemble accuracy: 100%"
Creates: 4 model files in models folder

Classification:

Shows: "Random Forest: MALICIOUS (98%)"
Shows: "SVM: MALICIOUS (96%)"
Shows: "Gradient Boosting: MALICIOUS (99%)"
Shows: "Neural Network: MALICIOUS (97%)"
Final: "ENSEMBLE DECISION: MALICIOUS (97.5%)"

Performance Evaluation:

Accuracy: 100%
Precision: 100%
Recall: 100%
F1-Score: 100%
Creates: confusion_matrix.png

YARA Generation:

Lists all IoCs found
Creates YARA rule file
Saves to outputs/yara_rules/


Quick Demonstration Flow
For Presentation (10 minutes):
1. Show ANY.RUN (3 minutes)

Upload sample
Show real-time execution
Point out key behaviors
Export results

2. Show Feature Extraction (1 minute)

Run script
Show 14 features extracted
Show CSV output

3. Show Model Training (2 minutes)

Run training script
Show 4 models training
Show 100% accuracy result

4. Show Classification (2 minutes)

Run on test sample
Show individual predictions
Show ensemble decision

5. Show YARA Generation (2 minutes)

Run intelligence generation
Show IoCs extracted
Show YARA rule created
