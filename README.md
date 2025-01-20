# Predict Recruiter Call - README

## Overview
This project provides a Python script to evaluate job descriptions and predict the likelihood of receiving a recruiter call based on:
- Your resume.
- Past successful job descriptions.

It uses OpenAI's GPT-3.5-turbo model to score job descriptions against a set of positive examples and your resume, outputting the top matches. The results include job URLs and are saved in a CSV file.

## Features
- Extracts text from PDFs for positive job examples and resume.
- Evaluates job descriptions from a CSV file.
- Outputs matching jobs along with their URLs to the console and a CSV file.
- Limits processing to the first 10 job descriptions for efficiency.

## Prerequisites
- Python 3.7+
- OpenAI API Key
- Required Python libraries:
  - `openai`
  - `pandas`
  - `PyPDF2`

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/predict-recruiter-call.git
   cd predict-recruiter-call
   ```

2. Install dependencies:
   ```bash
   pip install openai pandas PyPDF2
   ```

3. Set up your OpenAI API key:
   - Add your API key in the script at:
     ```python
     openai.api_key = 'your_openai_api_key_here'
     ```

4. Place your files:
   - Transformed job data in `data/job_data_transformed.csv`.
   - Positive job examples as PDFs in `data/positiveexample1.pdf` and `data/positiveexample2.pdf`.
   - Optional: Your resume as `data/resume.pdf`.

## Usage
1. Run the script:
   ```bash
   python script_name.py
   ```

2. The script will:
   - Process up to 10 job descriptions.
   - Evaluate matches against your positive examples and resume.
   - Print the URLs of matching jobs to the console.
   - Save the results to `jobs_to_apply.csv`.

## Output
- **Console**: Matching job URLs.
- **CSV File**: `jobs_to_apply.csv` with matching jobs and their details, including URLs.

## File Structure
```
project-root/
│
├── data/
│   ├── job_data_transformed.csv        # Job descriptions dataset
│   ├── positiveexample1.pdf           # Positive example 1
│   ├── positiveexample2.pdf           # Positive example 2
│   └── resume.pdf                     # Your resume (optional)
│
├── script_name.py                     # Main Python script
├── README.md                          # Project documentation
```

## Customization
- Adjust the match threshold in the script:
  ```python
  if prediction is not None and prediction > 0.7:  # Adjust threshold as needed
  ```
- Modify the limit on processed jobs:
  ```python
  job_data = job_data.head(10)  # Adjust the limit
  ```

## License
MIT License

## Contributions
Feel free to submit pull requests or raise issues for improvements.


