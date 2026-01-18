# Student Grade Management System

A Python-based console application for managing student grades with complete SDLC documentation.

## Table of Contents
- [Project Overview](#project-overview)
- [Software Development Life Cycle (SDLC)](#software-development-life-cycle-sdlc)
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)

## Project Overview

The Student Grade Management System is a command-line application that allows users to manage student records including their names, courses, and grades. The system provides functionality to add students, record grades, calculate averages, and generate reports.

---

## Software Development Life Cycle (SDLC)

### 1. Planning Phase

**Objective**: Develop a system to manage student grades efficiently.

**Stakeholders**:
- Students
- Teachers/Instructors
- School Administrators

**Project Scope**:
- Add and manage student records
- Record course grades
- Calculate grade averages
- Generate student reports
- View all students in the system

**Timeline**: 2 weeks development cycle

**Resources Required**:
- Python 3.x
- Development environment (VS Code, PyCharm, etc.)
- Git for version control

---

### 2. Analysis Phase

**Requirements Gathering**:

**Functional Requirements**:
1. The system must allow adding new students with unique IDs
2. The system must store student information (student_id, student_name, courses, grades)
3. The system must calculate grade_average for each student
4. The system must generate student_report showing all details
5. The system must display all students in the database
6. The system must validate input data

**Non-Functional Requirements**:
1. The system should be user-friendly with clear menu options
2. The system should handle errors gracefully
3. Data should persist during the session
4. Response time should be immediate for all operations

**Use Cases**:
- Add Student: User enters student_name and student_id
- Add Grade: User enters student_id, course_name, and grade_value
- Calculate Average: System computes grade_average automatically
- View Report: Display student_name, courses, grades, and grade_average
- List Students: Show all student records

---

### 3. Design Phase

**System Architecture**:
- Single-tier console application
- Object-Oriented Design with Student class

**Class Design**:

```
Class: Student
Attributes:
  - student_id: string
  - student_name: string
  - courses: dictionary {course_name: grade_value}
  
Methods:
  - add_course(course_name, grade_value): Add a course and grade
  - calculate_average(): Calculate grade_average
  - get_report(): Return student_report as string

Class: GradeManagementSystem
Attributes:
  - students_database: dictionary {student_id: Student object}
  
Methods:
  - add_student(student_id, student_name): Create new student
  - add_grade(student_id, course_name, grade_value): Add grade to student
  - view_student_report(student_id): Display student information
  - list_all_students(): Show all students
  - display_menu(): Show menu options
  - run(): Main program loop
```

**Data Structures**:
- `students_database`: Dictionary storing student_id as key and Student object as value
- `courses`: Dictionary within Student class storing course_name as key and grade_value as value

**User Interface Design**:
```
=== Student Grade Management System ===
1. Add Student
2. Add Grade
3. View Student Report
4. List All Students
5. Exit
Enter choice:
```

---

### 4. Implementation Phase

**Technology Stack**:
- Programming Language: Python 3.x
- Development Tools: Git, GitHub

**Coding Standards**:
- Use snake_case for variables and functions
- Use PascalCase for class names
- Add docstrings to all classes and methods
- Follow PEP 8 style guidelines

**Key Implementation Details**:
- Student class encapsulates student data and operations
- GradeManagementSystem class manages all students
- Input validation for numeric grades (0-100)
- Error handling for invalid student IDs

**File Structure**:
```
student-grade-system/
├── student_grade_system.py    # Main application file
├── README.md                   # This documentation
└── .gitignore                  # Git ignore file
```

---

### 5. Testing Phase

**Test Cases**:

**Test Case 1: Add Student**
- Input: student_id = "S001", student_name = "John Doe"
- Expected: Student added successfully
- Status: ✓ Pass

**Test Case 2: Add Grade**
- Input: student_id = "S001", course_name = "Mathematics", grade_value = 85
- Expected: Grade added successfully
- Status: ✓ Pass

**Test Case 3: Calculate Average**
- Input: Student with grades: Math=85, English=90, Science=88
- Expected: grade_average = 87.67
- Status: ✓ Pass

**Test Case 4: Invalid Grade**
- Input: grade_value = 150
- Expected: Error message "Grade must be between 0 and 100"
- Status: ✓ Pass

**Test Case 5: Invalid Student ID**
- Input: student_id = "S999" (non-existent)
- Expected: Error message "Student not found"
- Status: ✓ Pass

**Test Case 6: View Report**
- Input: student_id = "S001"
- Expected: Display student_name, courses, grades, and grade_average
- Status: ✓ Pass

---

### 6. Deployment Phase

**Deployment Steps**:

1. Create GitHub repository
```bash
git init
git add .
git commit -m "Initial commit: Student Grade Management System"
git branch -M main
git remote add origin https://github.com/yourusername/student-grade-system.git
git push -u origin main
```

2. Clone repository on target machine
```bash
git clone https://github.com/yourusername/student-grade-system.git
cd student-grade-system
```

3. Run the application
```bash
python student_grade_system.py
```

**System Requirements**:
- Python 3.6 or higher
- Operating System: Windows, macOS, or Linux
- Memory: Minimum 512 MB RAM
- Storage: 10 MB free space

---

### 7. Maintenance Phase

**Maintenance Activities**:

**Corrective Maintenance**:
- Fix bugs reported by users
- Handle edge cases in input validation

**Adaptive Maintenance**:
- Update for new Python versions
- Adapt to different operating systems

**Perfective Maintenance**:
- Add data persistence (save to file/database)
- Implement grade letter conversion (A, B, C, etc.)
- Add student search functionality
- Generate PDF reports

**Preventive Maintenance**:
- Regular code reviews
- Performance optimization
- Security updates

**Future Enhancements**:
1. Add database integration (SQLite)
2. Implement user authentication
3. Create graphical user interface (GUI)
4. Add export functionality (CSV, PDF)
5. Implement grade statistics and analytics
6. Add course prerequisites tracking

---

## Installation

1. Clone the repository:
```bash
git clone https://github.com/oreoluwab97-droid/sen-assignment.git
cd sen-assignment
```

2. Ensure Python 3.x is installed:
```bash
python --version
```

3. Run the application:
```bash
python student_grade_system.py
```

---

## Usage

### Starting the Application

Run the program:
```bash
python student_grade_system.py
```

### Menu Options

1. **Add Student**: Enter student_id and student_name to create a new record
2. **Add Grade**: Enter student_id, course_name, and grade_value to record a grade
3. **View Student Report**: Enter student_id to see complete student_report
4. **List All Students**: Display all students in students_database
5. **Exit**: Close the application

### Example Workflow

```
Step 1: Add a student
- Choose option 1
- Enter student_id: S001
- Enter student_name: Alice Johnson

Step 2: Add grades
- Choose option 2
- Enter student_id: S001
- Enter course_name: Mathematics
- Enter grade_value: 92

Step 3: View report
- Choose option 3
- Enter student_id: S001
- See complete student_report with grade_average
```

---

## Features

- **Student Management**: Add and track multiple students using unique student_id
- **Grade Recording**: Store grades for multiple courses per student
- **Automatic Calculation**: System calculates grade_average automatically
- **Comprehensive Reports**: View detailed student_report with all information
- **Input Validation**: Ensures grade_value is between 0 and 100
- **Error Handling**: Graceful handling of invalid inputs
- **User-Friendly Interface**: Clear menu-driven navigation

---

## Project Structure

```
student-grade-system/
│
├── student_grade_system.py
│   ├── Student Class
│   │   ├── __init__(student_id, student_name)
│   │   ├── add_course(course_name, grade_value)
│   │   ├── calculate_average()
│   │   └── get_report()
│   │
│   └── GradeManagementSystem Class
│       ├── __init__()
│       ├── add_student(student_id, student_name)
│       ├── add_grade(student_id, course_name, grade_value)
│       ├── view_student_report(student_id)
│       ├── list_all_students()
│       ├── display_menu()
│       └── run()
│
└── README.md
```

---

## Technologies Used

- **Python 3.x**: Core programming language
- **Object-Oriented Programming**: Design paradigm
- **Git**: Version control system
- **GitHub**: Repository hosting

---

## Nomenclature Mapping (Design → Implementation)

This table shows how design phase names match implementation:

| Design Phase Term | Implementation Term | Type |
|------------------|---------------------|------|
| student_id | student_id | Variable/Attribute |
| student_name | student_name | Variable/Attribute |
| course_name | course_name | Variable/Parameter |
| grade_value | grade_value | Variable/Parameter |
| grade_average | grade_average | Variable/Return Value |
| student_report | student_report | Variable/Method Output |
| students_database | students_database | Dictionary |
| courses | courses | Dictionary Attribute |
| Student | Student | Class Name |
| GradeManagementSystem | GradeManagementSystem | Class Name |
| add_course() | add_course() | Method Name |
| calculate_average() | calculate_average() | Method Name |
| get_report() | get_report() | Method Name |
| add_student() | add_student() | Method Name |
| add_grade() | add_grade() | Method Name |
| view_student_report() | view_student_report() | Method Name |
| list_all_students() | list_all_students() | Method Name |

---

## Author

- **Name**: Oreoluwa
- **GitHub**: [@oreoluwab97-droid](https://github.com/oreoluwab97-droid)
- **Course**: SEN Assignment
- **Date**: January 2026

---

## License

This project is created for educational purposes as part of university coursework.

---

## Acknowledgments

- Course Instructor and SEN Department
- Software Engineering principles and SDLC methodology
- Python documentation and community
