Student Result Management System

A menu-driven command-line Student Result Management System developed using Python and OpenPyXL. The application allows users to add student academic results, calculate total marks and percentage, assign grades, check PASS/FAIL status, search individual student records, and display all stored results.

Student records are stored permanently in an Excel file (student_results.xlsx).

📌 About the Project

The Student Result Management System is a beginner-friendly Python CLI project created as part of a Python course.

The system collects the following information from the user:

Roll Number
Student Name
Class/Course
OS Marks
CP Marks
TCO Marks
ML Marks
ES Marks

After entering the marks, the program automatically calculates:

Total Marks
Percentage
Grade
PASS/FAIL Status

The student information and result are then stored in an Excel workbook using the OpenPyXL library.

✨ Key Features
👨‍🎓 1. Add Student Result

The user can add a new student by entering:

Roll Number
Name
Class/Course
Marks for five subjects

The system automatically calculates the student's result and saves it to Excel.

🔍 2. Get Student Result

The user can enter a student's Roll Number to search for a particular student.

The system displays:

Roll Number
Name
Class
OS
CP
TCO
ML
ES
Total
Percentage
Grade
Status

If the Roll Number does not exist, the system displays:

Student record not found.
📋 3. Show All Student Results

This option displays all student records stored in the Excel file.

The program reads the records directly from student_results.xlsx.

🚫 4. Duplicate Roll Number Checking

The system checks existing records before adding a new student.

If the Roll Number already exists, it displays:

Roll No already exists!

This prevents duplicate student records.

✅ 5. Marks Validation

The system accepts marks only between:

0 and 100

If the user enters marks outside this range, the program displays:

Marks must be between 0 and 100.
🧮 6. Automatic Result Calculation

The program automatically calculates the total:

Total = OS + CP + TCO + ML + ES

Percentage is calculated using:

Percentage = Total / 5
🏆 Grading System

The project uses the following grading system:

Percentage	Grade
90% and above	A+
80% – 89%	A
70% – 79%	B
60% – 69%	C
50% – 59%	D
Below 50%	E
📌 PASS/FAIL Condition

A student receives PASS only when all five subjects have at least 35 marks.

The program uses:

all(mark >= 35 for mark in marks)

Therefore:

Every subject >= 35 → PASS
Any subject < 35    → FAIL

If any subject is below 35, the grade is:

F

and the status becomes:

FAIL
🖥️ Application Menu

When the program starts, the following menu is displayed:

1. Add Student Result
2. Get Student Result
3. Show All Student Results
4. Exit

Enter your choice:
1️⃣ Add Student Result

When the user selects option 1, the program asks for student information.

Example:

Enter Roll No: 1
Enter Student Name: Ganesh Patil
Enter Class/Course: T.Y. / B-tech

Enter Marks for OS: 78
Enter Marks for CP: 67
Enter Marks for TCO: 87
Enter Marks for ML: 76
Enter Marks for ES: 89

The program calculates:

Total Marks: 397
Percentage: 79.40%
Grade: B
Result Status: PASS

The result is then saved in:

student_results.xlsx
2️⃣ Get Student Result

Select:

2. Get Student Result

Then enter the Roll Number:

Enter Roll No: 1

The program displays:

Roll No: 1
Name: Ganesh Patil
Class: T.Y. / B-tech
OS: 78
CP: 67
TCO: 87
ML: 76
ES: 89
Total: 397
Percentage: 79.40%
Grade: B
Status: PASS
3️⃣ Show All Student Results

Select:

3. Show All Student Results

The program reads all records from the Excel file and displays the available student information.

Example:

Roll No: 1
Name: Ganesh Patil
Class: T.Y. / B-tech
Total: 397
Percentage: 79.40%
Grade: B
Status: PASS
4️⃣ Exit

Select:

4. Exit

The program displays:

Thank you for visiting

and closes the application.

📊 Sample Student Record

The following is an example of the student data stored by the project:

Roll No	Name	Class	OS	CP	TCO	ML	ES	Total	Percentage	Grade	Status
1	Ganesh Patil	T.Y. / B-tech	78	67	87	76	89	397	79.40%	B	PASS
Calculation
OS  = 78
CP  = 67
TCO = 87
ML  = 76
ES  = 89

Total = 78 + 67 + 87 + 76 + 89
      = 397

Percentage = 397 / 5
           = 79.40%

Grade = B
Status = PASS
📁 Excel Data Storage

The project automatically creates an Excel file if it does not already exist.

File Name
student_results.xlsx
Excel Sheet Name
Student Results
Excel Columns
Column	Description
Roll No	Unique student Roll Number
Name	Student Name
Class	Class/Course
OS	Operating System Marks
CP	Computer Programming Marks
TCO	TCO Marks
ML	Machine Learning Marks
ES	ES Marks
Total	Total Marks
Percentage	Percentage
Grade	Assigned Grade
Status	PASS/FAIL
🛠️ Technologies Used
🐍 Python 3
📊 OpenPyXL
📗 Microsoft Excel
💻 Command Line Interface (CLI)
📚 Python Concepts Used

This project demonstrates the following Python concepts:

Variables
Data Types
input()
print()
Lists
Functions
Function parameters
Return values
if
elif
else
for loop
while loop
all()
sum()
Arithmetic operators
Comparison operators
Logical operators
String formatting
Input validation
File handling
Excel file operations
Reading Excel data
Writing Excel data
🔧 Functions Used

The project is divided into different functions to keep the code organized.

create_excel_file()

Creates the Excel workbook if it does not already exist and adds the required column headers.

calculate_result(marks)

Calculates:

Total
Percentage
Grade
PASS/FAIL status

and returns the calculated values.

add_student()

Collects student information and marks, validates the input, calculates the result, and saves the student record to Excel.

get_result()

Searches for a student using their Roll Number and displays their complete result.

show_all_data()

Reads the Excel file and displays all available student records.

menu()

Displays the main menu and controls the complete application.

🔄 Project Working Flow
                ┌──────────────────────┐
                │        START         │
                └──────────┬───────────┘
                           ↓
                ┌──────────────────────┐
                │ Check / Create Excel │
                │ student_results.xlsx │
                └──────────┬───────────┘
                           ↓
                ┌──────────────────────┐
                │      MAIN MENU       │
                ├──────────────────────┤
                │ 1. Add Result        │
                │ 2. Get Result        │
                │ 3. Show All Results  │
                │ 4. Exit              │
                └──────────┬───────────┘
                           ↓
                     Enter Choice
                           ↓
          ┌────────────────┼────────────────┐
          ↓                ↓                ↓
    ┌───────────┐    ┌───────────┐    ┌────────────┐
    │ Add Result│    │ Get Result│    │ Show All   │
    └─────┬─────┘    └─────┬─────┘    │ Results    │
          ↓                ↓           └──────┬─────┘
    Enter Student      Enter Roll No.        ↓
    Information             ↓           Read Excel
          ↓             Search Record        ↓
    Enter 5 Marks           ↓           Display Data
          ↓             Show Result
    Calculate Result
          ↓
    Save to Excel
          ↓
          └────────────────┬────────────────┘
                           ↓
                    Return to Menu
                           ↓
                     Exit Selected?
                       /       \
                     No         Yes
                     ↓           ↓
                  Menu         EXIT
📂 Project Structure
python-course/
│
├── Student_Result_Management_System.py
├── student_results.xlsx
└── README.md
Student_Result_Management_System.py

Contains the complete Python source code of the Student Result Management System.

student_results.xlsx

Stores student academic records.

README.md

Contains project documentation and usage information.

▶️ How to Run
Step 1 — Install Python

Make sure Python 3 is installed.

Check your Python version:

python --version
Step 2 — Install OpenPyXL

Install the required library:

pip install openpyxl
Step 3 — Run the Program

Open the project folder in the terminal and run:

python Student_Result_Management_System.py
🎯 Project Objectives

The main objectives of this project are:

To practice Python programming.
To understand functions and loops.
To work with conditional statements.
To perform automatic result calculations.
To validate user input.
To learn Excel file handling using OpenPyXL.
To store student records permanently.
To create a practical command-line application.