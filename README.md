🎓 Certificate Generator

This is a Python project to automatically generate certificates for students/participants using data from a CSV file.
The script dynamically fills participant details (such as Name, Roll Number, Branch, Hackathon/Event Name, Topic, and Date) into a certificate template and adds the Principal’s signature in a signature-style font.

📂 Project Structure
certificate-generator/
│── certificate.py              # Main script to generate certificates
│── signature_font.ttf           # Signature-style font (e.g., GreatVibes-Regular.ttf)
│── template.png                 # Certificate template image
│── students.csv                 # CSV file with student/participant data
│── generated_certificates/      # Generated certificates will be saved here
│── README.md                    # Project documentation

✨ Features

📑 Dynamic Certificate Content – Automatically inserts student details into the certificate.

🖋️ Signature Font Support – Adds the Principal’s name in a signature-style font.

🖼️ Template Based – Works with any background certificate template (template.png).

🔄 Batch Generation – Reads all student details from students.csv and generates certificates in one go.

💾 Organized Output – Certificates are saved in the generated_certificates/ folder.

🛠️ Requirements

Python 3.9+ (tested with Python 3.11)

Install dependencies:

pip install pillow pandas

📊 CSV Format

The students.csv should contain details in this format:

Name,Roll_No,Branch,Hackathon_Name,Topic,Date
TAMMANA SRI LAKSHMI VASANTHI,23B21A4202,CSE,Smart India Hackathon,AI Attendance System,2025-08-20
YANDAPALLI SAI VARSHITHA,23B21A4305,IT,Smart India Hackathon,Blockchain Security,2025-08-20

▶️ How to Run

Place your certificate template as template.png in the project folder.

Add a signature font file (e.g., GreatVibes-Regular.ttf) as signature_font.ttf.

Update students.csv with participant details.

Run the script:

python certificate.py


Certificates will be saved in the generated_certificates/ folder, named after each student.

🖥️ Usage Example

Here’s a quick look at how the script processes the CSV file:

import pandas as pd
from certificate import generate_certificate  # function from certificate.py

# Load student data
students = pd.read_csv("students.csv")

# Loop through each student and generate certificate
for index, row in students.iterrows():
    generate_certificate(
        row["Name"],
        row["Roll_No"],
        row["Branch"],
        row["Hackathon_Name"],
        row["Topic"],
        row["Date"]
    )

print("✅ Certificates generated successfully in 'generated_certificates/' folder!")

📜 Example Output

✅ Each certificate includes:

Student details from the CSV file.

Professional text formatting.

Principal’s signature in signature_font.ttf.

Designation neatly placed below the signature.

🖼️ Sample Output Screenshot

Here is an example of a generated certificate:

(Replace sample_certificate.png with one of your generated certificate images for GitHub preview.)

👩‍🏫 Credits

Developed by: Vasanthi Tammana

Fonts Used: Arial (for body text), Great Vibes (for signature).

Tools: Python, Pillow, Pandas