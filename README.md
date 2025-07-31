# PIYSUH - Resume-Parser---Real-time-Project
I have Developed an intelligent resume parsing tool using Python NLP technique to automatically extract key information from .pdf and .docx resumes. The parser efficiently identifies and structures relevant details into a clean CSV format, enabling fast analysis and integration with downstream systems like ATS or databases.
Healthcare + IT Resume Parser designed to extract structured data (like name, email, phone number, job title, experience, skills, etc.) from a wide variety of resume files — PDFs, Word documents, RTFs, images, and HTML/TXT. It categorizes skills into Profession, Specialization, and Other IT/Soft Skills, making it suitable for recruiting or HR analytics workflows.

These libraries serve specific purposes:

os: File handling

re: Regex for pattern matching (emails, phones)

pandas: Storing structured results in Excel

pypandoc: Converts RTF/DOC to text

pdfplumber: Reads PDFs

docx: Reads .docx files

pytesseract + PIL: OCR for image-based resumes

spacy: NLP to extract names, organizations, etc

 loads a small English NLP model to detect entities (like PERSON, ORG, etc.).
skills from resume content using whole-word matching.
Allows detection of U.S. states from resumes (helpful in location mapping).
 Helper Function for Whole-Word Matching This avoids partial matches (e.g., "Analyst" being matched in "Financial Analyst").
 pdf → via pdfplumber

.docx → via python-docx

.doc, .rtf → via pypandoc

.png, .jpg → via OCR (pytesseract)

.txt, .html → via regular open/read

Key Extraction Logic:
Field	Method
Name	Uses spaCy to detect PERSON entities
Email	Regex match
Phone Number	Flexible US phone regex
Company Name	First ORG detected
Job Title	Regex for “is a…” or “works as…” pattern
US State	Searches known state names
Experience Description	First 2 NLP sentences
Skill1 (Professions)	Matches from professions list
Skill2 (Specialties)	Matches from specialties list
Skill3 (Other skills)	Matches from other_skills list
