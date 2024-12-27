# GAIA OpenAI Validation

## GAIA Benchmarking App: A Streamlit Application for Validation Testing

This project presents a web-based application that validates test cases from the **GAIA Dataset** using OpenAI’s language models (LLM). Users can interactively select test cases, send them to OpenAI, and compare the AI-generated responses with predefined answers. If OpenAI’s response doesn’t match the expected outcome, users are given the flexibility to modify the validation steps and re-submit the question for another validation attempt.

---

## Project Resources

- **Google Codelab**: [Codelab Link](https://codelabs-preview.appspot.com/?file_id=1KwPr7VIQyALeQtxgZByGq4Vxe8GnI5_oMPFem20HR4Y#0)
- **App (Streamlit Cloud)**: [Streamlit Link](https://gaia-openai-validation-apmepvhff4kwcxfy687eqr.streamlit.app/)
- **YouTube Demo**: [Demo Link](https://youtu.be/XyujyicHOaA?feature=shared)

---

# Technologies

![Streamlit](https://img.shields.io/badge/-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![AWS](https://img.shields.io/badge/Amazon%20AWS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Python](https://img.shields.io/badge/-Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/-Pandas-150458?style=for-the-badge&logo=pandas)
![S3](https://img.shields.io/badge/-AWS_S3-569A31?style=for-the-badge&logo=amazon-s3&logoColor=white)
![RDS](https://img.shields.io/badge/AWS_RDS-527FFF?style=for-the-badge&logo=amazon-rds&logoColor=white)
![Hugging Face](https://img.shields.io/badge/-HuggingFace-FFD54F?style=for-the-badge&logo=huggingface&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

---

## Architecture Diagram

![flow_diagram](https://github.com/user-attachments/assets/2eac7279-2400-4c39-b865-3737c244130a)

---

## Project Flow

### Step 1: Selection of Test Cases

- The User opens the application and selects a validation test case from the GAIA Dataset.
- Predefined questions and answers from the metadata table are displayed for user reference.

### Step 2: Sending Questions to OpenAI

- The selected question is submitted to the OpenAI GPT Model.
- The OpenAI response is compared with the predefined answer.

### Step 3: Validating the Answer

- **Correct-as-is**: If the response matches the predefined answer, it is categorized as such and saved to the model response table.
- **Correct-after-steps**: If the response doesn't match, users can modify the validation steps and resubmit the question. If the modified response is correct, it’s saved as "Correct-after-steps."
- **Wrong Answer**: If the response remains incorrect even after modification, it’s labeled as "Wrong Answer."

---

## Repository Structure

```bash
GAIA-OPENAI-VALIDATION/
├── architecture_diagram/
│   ├── input_icons/
│   │   ├── flow_diagram.ipynb
│   │   ├── flow_diagram.png
├── data/
│   ├── data_read.py
│   ├── data_s3.py
│   ├── data_storage.py
│   ├── data_storage_log.py
│   └── db_connection.py
├── openai_api/
│   ├── openai_api_call.py
│   └── openai_api_streamlit.py
├── pages/
│   ├── 1_Predicting.py
│   └── 2_Dashboard.py
├── project_logging/
│   └── logging_module.py
├── .env.example
├── Home.py
├── README.md
└── requirements.txt

```

---

## Prerequisites

Before running the application, ensure that Python is installed:

1. **Python 3.8+**: [Download Python](https://www.python.org/downloads/)

---

---

## Prerequisites

Before running the application, ensure the following:

1. **Python 3.8+**: [Download Python](https://www.python.org/downloads/)
2. **Conda** (optional, for managing environments): [Install Miniconda/Anaconda](https://docs.conda.io/en/latest/miniconda.html)

---

## Setting Up the Environment

Follow these steps to set up and run the application:

### Step 1: Clone the Repository

```bash
git clone https://github.com/Dipenpatel3/Gaia-openai-validation.git
cd Gaia-openai-validation
```

If you prefer not to use `conda`, ensure Python is installed and skip to Step 3.

### Step 2: Create a Conda Environment (Optional)

1. Create a `conda` environment:

   ```bash
   conda create -n gaia_env python=3.8 -y
   ```

2. Activate the environment:

   ```bash
   conda activate gaia_env
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Step 3: Running the Application

1. Ensure the environment is activated (if using `conda`):

   ```bash
   conda activate gaia_env
   ```

2. Run the Streamlit application using the `home.py` file:
   ```bash
   streamlit run Home.py
   ```

---

## Contact

For Any questions or support, please contact [Dipen Patel](mailto:dipenpatel98.dp@gmail.com).
