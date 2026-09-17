<div align="center">

# Student Task Manager

### A Lightweight Java Console Application for Academic Task and Deadline Management

**Java | OOP | Collections | File I/O | Console Application**

</div>

---

## 1. Project Overview

**Student Task Manager** is a small, lightweight, and modular Java console application designed to help college students organize academic assignments, tasks, priorities, deadlines, and completion status.

The application provides a simple menu-driven interface through which students can create, view, update, delete, search, filter, and manage their academic tasks.

The project is intentionally designed without databases, web frameworks, cloud services, or external APIs. It focuses on core Java programming concepts, Object-Oriented Programming, collections, file handling, validation, exception handling, and basic software testing.

---

## 2. Problem Statement

College students frequently manage assignments, laboratory work, projects, and academic deadlines manually. Maintaining this information across notebooks, messages, or multiple applications can make it difficult to track pending work and approaching deadlines.

The Student Task Manager provides a centralized and simple solution for maintaining academic tasks in a local text file while allowing students to quickly search, filter, update, and track their progress.

---

## 3. Project Objectives

The primary objectives of this project are:

* To create a simple academic task management system.
* To allow students to maintain assignment and task information.
* To track task priorities and due dates.
* To provide task searching and filtering facilities.
* To track pending and completed tasks.
* To identify overdue tasks.
* To generate basic task statistics.
* To demonstrate Java OOP concepts.
* To demonstrate Java Collections Framework.
* To implement persistent storage using Java File I/O.
* To handle invalid user input safely.
* To maintain a modular and maintainable project structure.

---

## 4. Key Features

### Task Management

* Add new tasks.
* View all available tasks.
* Update existing tasks.
* Delete tasks.
* Prevent duplicate task IDs.

### Search and Filter

* Search tasks by title.
* Search tasks by subject.
* Filter tasks by priority.
* Filter tasks by status.
* Display overdue pending tasks.

### Task Status

* Mark a task as completed.
* Mark a task as pending.
* Display completed tasks.
* Display pending tasks.

### Task Reporting

The application provides a simple report containing:

* Total number of tasks.
* Number of completed tasks.
* Number of pending tasks.
* Number of high-priority tasks.
* Number of overdue tasks.

### Persistent Storage

Tasks are stored locally in:

```text
data/tasks.txt
```

The application:

1. Loads saved tasks when it starts.
2. Updates the in-memory task list.
3. Saves changes to the file.
4. Restores the tasks when the application is started again.

---

## 5. Functional Modules

The project contains four major functional modules.

| Module               | Description                                      |
| -------------------- | ------------------------------------------------ |
| Task Management      | Add, view, update and delete tasks               |
| Task Search & Filter | Search and filter tasks using different criteria |
| Task Status          | Manage pending and completed tasks               |
| Simple Report        | Display task statistics                          |

---

## 6. Task Information

Each task contains the following information:

| Field    | Description                          |
| -------- | ------------------------------------ |
| Task ID  | Unique numeric identifier            |
| Title    | Name of the academic task            |
| Subject  | Subject associated with the task     |
| Priority | LOW, MEDIUM or HIGH                  |
| Due Date | Task deadline in `dd-MM-yyyy` format |
| Status   | PENDING or COMPLETED                 |

### Example

```text
ID: 101
Title: Complete DBMS Assignment
Subject: DBMS
Priority: HIGH
Due Date: 10-09-2026
Status: PENDING
```

---

## 7. Technology Stack

The project intentionally uses only basic Java technologies.

### Core Technologies

* Java
* Java Collections Framework
* Java File I/O
* Object-Oriented Programming
* Java Exception Handling
* Java Enums

### Application Type

```text
Console-Based Java Application
```

### Technologies Not Used

The project does not require:

* React
* Next.js
* JavaScript
* Python
* Spring Boot
* MySQL
* REST APIs
* External APIs
* Cloud deployment
* Microservices
* Complex frameworks

This keeps the project small, understandable, and suitable for an academic demonstration.

---

## 8. OOP Concepts Used

### Encapsulation

Task properties are private and accessed using getters and setters.

```java
private int id;
private String title;
private String subject;
```

### Classes and Objects

The project uses separate classes for tasks, task management, validation, storage, reporting, and application control.

### Constructors

Constructors initialize task objects with their required information.

### Methods

Each class contains methods responsible for specific operations.

### Enums

Two enums are used:

```text
Priority
    LOW
    MEDIUM
    HIGH
```

```text
Status
    PENDING
    COMPLETED
```

### Collections

An `ArrayList<Task>` is used to maintain tasks in memory.

### Exception Handling

Invalid input, invalid dates, duplicate IDs, and other normal input errors are handled without terminating the application.

---

## 9. Project Architecture

The application follows a simple modular architecture.

```text
                 +----------------------+
                 |        Student       |
                 +----------+-----------+
                            |
                            v
                 +----------------------+
                 |    Main Console UI    |
                 +----------+-----------+
                            |
                            v
                 +----------------------+
                 |     TaskManager       |
                 +----+------+------+---+
                      |      |      |
                      v      v      v
                Validator  Storage  Report
                           |
                           v
                    data/tasks.txt
```

### Main Components

| Class             | Responsibility                    |
| ----------------- | --------------------------------- |
| `Main`            | Console menu and user interaction |
| `Task`            | Stores task information           |
| `TaskManager`     | Performs task operations          |
| `TaskValidator`   | Validates user input              |
| `FileStorage`     | Loads and saves tasks             |
| `ReportGenerator` | Generates task statistics         |
| `Priority`        | Defines task priority values      |
| `Status`          | Defines task status values        |

---

## 10. Project Structure

```text
StudentTaskManager/
│
├── src/
│   ├── Main.java
│   ├── Task.java
│   ├── TaskManager.java
│   ├── TaskValidator.java
│   ├── FileStorage.java
│   ├── ReportGenerator.java
│   ├── Priority.java
│   └── Status.java
│
├── data/
│   └── tasks.txt
│
├── test/
│   └── TaskManagerTest.java
│
├── docs/
│   ├── diagrams.md
│   └── report.md
│
├── README.md
└── statement.md
```

---

## 11. Requirements

### Software Requirements

* JDK 17 or later
* Windows, Linux, or macOS
* Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or Eclipse

### Verify Java Installation

```powershell
java -version
```

```powershell
javac -version
```

---

## 12. Installation

Clone or download the project repository.

Open a terminal inside the project directory.

Example Windows location:

```text
C:\Users\mridu\Downloads\StudentTaskManager\StudentTaskManager
```

---

## 13. Compilation

### Windows PowerShell

PowerShell does not expand `src/*.java` in the same way as some Unix shells. Use:

```powershell
javac -d out (Get-ChildItem src\*.java) test\TaskManagerTest.java
```

### Command Prompt

```cmd
javac -d out src\*.java test\TaskManagerTest.java
```

The compiled `.class` files will be placed inside the `out` directory.

---

## 14. Running the Application

After successful compilation:

```powershell
java -cp out Main
```

The application displays the main menu.

```text
================================
       STUDENT TASK MANAGER
================================
1. Add Task
2. View All Tasks
3. Update Task
4. Delete Task
5. Search Task
6. Filter Tasks
7. Mark Task Complete
8. Mark Task Pending
9. Task Report
10. Exit

Enter choice:
```

The menu continues running until the user selects option `10`.

---

## 15. Testing

The project contains:

```text
test/TaskManagerTest.java
```

Compile it together with the source files:

```powershell
javac -d out (Get-ChildItem src\*.java) test\TaskManagerTest.java
```

Run the tests:

```powershell
java -cp out TaskManagerTest
```

The test program verifies:

* Adding a task
* Updating a task
* Searching for a task
* Filtering tasks
* Completing a task
* Deleting a task
* File storage
* Duplicate task ID validation

Expected final output:

```text
All tests passed.
```

---

## 16. Data Storage

The application uses a simple text file instead of a database.

Location:

```text
data/tasks.txt
```

### Record Format

```text
ID|TITLE|SUBJECT|PRIORITY|DUE_DATE|STATUS
```

### Example

```text
101|Complete DBMS Assignment|DBMS|HIGH|10-09-2026|PENDING
102|Java Lab Record|Java|MEDIUM|12-09-2026|PENDING
```

The `|` character separates individual task fields.

---

## 17. Input Validation

The application validates normal user input before processing it.

### Validations Implemented

* Empty task title
* Empty subject
* Invalid task ID
* Duplicate task ID
* Invalid priority
* Invalid status
* Invalid date format
* Unsupported data values
* Invalid menu choices

### Date Format

The required date format is:

```text
dd-MM-yyyy
```

Example:

```text
10-09-2026
```

Invalid input produces a clear error message instead of crashing the application.

---

## 18. Non-Functional Requirements

### Usability

The application uses a simple numbered console menu and clear messages, making it easy for students to operate.

### Performance

Tasks are maintained in an `ArrayList`, which is suitable for the small amount of data expected in an academic task manager.

### Reliability

Input validation and exception handling prevent common invalid inputs from terminating the application.

### Maintainability

The application is divided into multiple focused classes, making the code easier to understand, modify, and debug.

### Security

The application is local and does not expose network services or depend on external APIs.

### Resource Efficiency

The project uses lightweight Java objects and a small text file instead of requiring a database server or other infrastructure.

---

## 19. Testing Strategy

Testing focuses on the core functionality of the application.

| Test          | Purpose                          |
| ------------- | -------------------------------- |
| Add Task      | Verify task creation             |
| Update Task   | Verify task modification         |
| Delete Task   | Verify task removal              |
| Search Task   | Verify title/subject search      |
| Filter Task   | Verify priority/status filtering |
| Complete Task | Verify status change             |
| Validation    | Verify invalid input handling    |
| File Storage  | Verify persistence               |

---

## 20. Design Documentation

The `docs/` directory contains the project's design documentation.

### `docs/diagrams.md`

Contains Mermaid diagrams for:

1. System Architecture
2. User Workflow
3. Use Case Diagram
4. Class Diagram
5. Sequence Diagram
6. Data/Storage Design

### `docs/report.md`

Contains concise report-ready content covering:

* Introduction
* Problem Statement
* Functional Requirements
* Non-Functional Requirements
* Architecture
* Design Decisions
* Implementation
* Testing
* Challenges
* Learnings
* Future Enhancements
* References

---

## 21. Workflow

The basic application workflow is:

```text
Start
  |
  v
Load tasks from file
  |
  v
Display Main Menu
  |
  v
Select Operation
  |
  +---- Add/Update/Delete ----> Validate Input
  |                                |
  |                                v
  |                            Update List
  |                                |
  |                                v
  |                            Save File
  |
  +---- Search/Filter ----------> Display Results
  |
  +---- Status Change ----------> Save File
  |
  +---- Report -----------------> Display Statistics
  |
  +---- Exit -------------------> End
```

---

## 22. Design Decisions

### Why Console Application?

A console interface keeps the project simple and focuses on Java programming fundamentals rather than UI frameworks.

### Why ArrayList?

The application is intended for a small number of student tasks, making `ArrayList` a simple and appropriate collection.

### Why Text File?

File storage provides persistence without the complexity of setting up and managing a database.

### Why Enums?

`Priority` and `Status` enums restrict values to valid predefined choices.

### Why Separate Classes?

Separating responsibilities makes the project easier to understand, test, maintain, and explain during a viva.

---

## 23. Challenges Faced

Some important implementation challenges include:

* Handling invalid console input.
* Validating task IDs.
* Preventing duplicate task IDs.
* Validating dates.
* Maintaining consistent file records.
* Loading saved data correctly.
* Keeping the project modular without unnecessary complexity.

---

## 24. Learning Outcomes

This project provides practical understanding of:

* Java programming
* Object-Oriented Programming
* Encapsulation
* Classes and objects
* Constructors
* Methods
* Enums
* Java Collections
* File I/O
* Exception handling
* Input validation
* Modular programming
* Basic software testing

---

## 25. Future Enhancements

The current implementation intentionally remains small. Possible future improvements include:

* Sorting tasks by due date.
* Adding task categories.
* Adding reminder notifications.
* Exporting reports.
* Adding a graphical user interface.
* Adding optional user authentication.
* Adding calendar integration.
* Migrating from text-file storage to a database.

These features are outside the scope of the current version.

---

## 26. Scope Limitations

The current project does not include:

* Login or authentication
* Admin panel
* Database server
* Web application
* Cloud deployment
* Artificial Intelligence
* Machine Learning
* Payment systems
* REST APIs
* Microservices
* External APIs

These limitations are intentional to keep the project focused on core Java concepts.

---

## 27. Viva Explanation

The project can be explained in five simple steps:

```text
1. Main
   ↓
   Takes input from the student.

2. Task
   ↓
   Stores task information.

3. TaskManager
   ↓
   Performs CRUD, search, filter and status operations.

4. FileStorage
   ↓
   Saves and loads tasks from tasks.txt.

5. ReportGenerator
   ↓
   Calculates and displays task statistics.
```

### One-Line Project Explanation

> Student Task Manager is a Java console application that uses OOP, collections, validation, and file I/O to help students manage academic tasks, deadlines, priorities, and completion status.

---

## 28. Repository Contents

The repository contains:

```text
Source Code
    |
    +-- Java Classes
    +-- Enums
    +-- Validation
    +-- File Storage
    +-- Testing

Documentation
    |
    +-- README
    +-- Project Statement
    +-- Design Diagrams
    +-- Report Content

Data
    |
    +-- Sample Task Records
```

---

## 29. Quick Start

For Windows PowerShell:

```powershell
cd "C:\Users\mridu\Downloads\StudentTaskManager\StudentTaskManager"
```

Compile:

```powershell
javac -d out (Get-ChildItem src\*.java) test\TaskManagerTest.java
```

Test:

```powershell
java -cp out TaskManagerTest
```

Run:

```powershell
java -cp out Main
```

---

## 30. Project Status

**Project Type:** Academic Java Project
**Application:** Console-Based
**Language:** Java
**Storage:** Text File
**Architecture:** Modular OOP
**Testing:** Included
**Documentation:** Included
**External Database:** Not Required
**External APIs:** Not Required

---

<div align="center">

## Student Task Manager

**Simple. Modular. Practical.**

A Java-based academic task management project designed for learning, demonstration, and viva evaluation.

</div>
