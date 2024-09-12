### Job-Recommendation-systemusing-machine-learning
# 🏆 **Job Recommendation System** 

> A powerful job recommendation system that extracts skills from resumes and helps match them with relevant job opportunities.

![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![Spacy](https://img.shields.io/badge/spacy-3.0+-green)
![PyMuPDF](https://img.shields.io/badge/pymupdf-1.19.6-orange)

## ✨ **Key Features**
- 🧑‍💻 **Extract Skills from Resumes**: Automatically extracts key skills from PDFs using **NLP**.
- 🗃️ **Job Matching**: Can be used to match candidates' skills with job descriptions.
- ⚡ **Fast and Efficient**: Uses **PyMuPDF** for PDF extraction and **spaCy** for Named Entity Recognition (NER).

---

## 📥 **Installation**

1. Install the required libraries:
   ```bash
   pip install pymupdf spacy
2. Download the English language model for spaCy:
   ```bash
   python -m spacy download en_core_web_sm
3. ## 🛠️ How to Use

### 1. Import the necessary libraries:

```python
import fitz  # PyMuPDF for PDF processing
import spacy  # spaCy for NLP


Here’s the README code in markdown format, without rendering the output, so you can use it directly in your project:

markdown
Copy code
# 🚀 Skill Extractor from PDF Resume

A Python tool to extract skills from a PDF resume using `PyMuPDF` for PDF processing and `spaCy` for Natural Language Processing.

## 🛠️ How to Use

### 1. Import the necessary libraries:

```python
import fitz  # PyMuPDF for PDF processing
import spacy  # spaCy for NLP
2. Load the spaCy NLP model:
python
Copy code
nlp = spacy.load('en_core_web_sm')
3. Extract Text from PDF:
Here’s a function to extract text from each page of a PDF:

python
Copy code
def extract_text_from_pdf(pdf_path):
    document = fitz.open(pdf_path)
    text = ''
    for page_num in range(len(document)):
        page = document.load_page(page_num)
        text += page.get_text()
    return text
4. Extract Skills from the Text:
Now, extract relevant skills like organization names or product names:

python
Copy code
def extract_skills_from_text(text):
    doc = nlp(text)
    skills = set()
    for ent in doc.ents:
        if ent.label_ in ['ORG', 'PRODUCT']:  # Customize labels as needed
            skills.add(ent.text)
    return ', '.join(skills)
5. Use the Functions:
Finally, pass your PDF resume path and extract the skills:

python
Copy code
resume_text = extract_text_from_pdf('path_to_your_resume.pdf')
extracted_skills = extract_skills_from_text(resume_text)
print(f"Extracted Skills: {extracted_skills}")
🔥 Example Output:
python
Copy code
Extracted Skills: Facebook, Google, Python, TensorFlow
🎯 Key Features:
Extracts text from a PDF resume file using PyMuPDF.
Identifies skills by recognizing organizations and products with spaCy.
Easy to extend for other types of Named Entities (e.g., skills, locations).
🛠️ Technologies Used:
Language: Python 🐍
Libraries:
PyMuPDF for PDF processing 📄
spaCy for Natural Language Processing 🤖
📝 Installation
Clone the repository:
bash
Copy code
git clone https://github.com/your-repo/skill-extractor.git
Install the required libraries:
bash
Copy code
pip install -r requirements.txt
Alternatively, install directly:
bash
Copy code
pip install spacy pymupdf
Download spaCy's English model:
bash
Copy code
python -m spacy download en_core_web_sm
🤝 Contributing
We welcome contributions! Feel free to submit a pull request or raise an issue. Let's make this tool even better.

📄 License
This project is licensed under the MIT License.

👤 Author
Developed by Shubham Kumar. Connect with me on LinkedIn.

Happy Coding! 😄
css
Copy code

This is the complete `README.md` code in markdown format that you can use in yo
