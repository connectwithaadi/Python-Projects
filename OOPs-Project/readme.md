# 🏥 Hospital Management System

A menu-driven **Hospital Management System built in Python** to demonstrate core **Object-Oriented Programming (OOP)** concepts through a practical hospital workflow.

The system manages patients, doctors, wards, appointments, billing, medical history, and hospital statistics using an in-memory object-oriented design.

---

## 📌 Project Overview

This project demonstrates how real-world hospital entities can be modeled using Python classes and how different OOP concepts can be applied to build a structured management system.

The system supports:

* 👤 Patient registration and management
* 👨‍⚕️ Doctor registration
* 🏥 Ward and bed management
* 📅 Appointment booking
* 🩺 Appointment completion and diagnosis
* 💳 Billing and bill items
* 💰 Bill payments
* 📋 Patient medical history
* 📊 Hospital statistics
* ⚠️ Custom exception handling
* 🖥️ Menu-driven Command Line Interface

---

## 🧠 OOP Concepts Demonstrated

### 1. Encapsulation

Private attributes and properties are used to control access and validation of data.

Examples:

* Patient information
* Doctor schedules
* Ward bed capacity
* Bill payment and balance

### 2. Abstraction

`Person` is implemented as an abstract base class using `ABC` and `abstractmethod`.

```python
class Person(ABC):
    @abstractmethod
    def get_role(self):
        pass
```

### 3. Inheritance

`Patient` and `Doctor` inherit common properties and behavior from the `Person` class.

```text
             Person
             /    \
        Patient   Doctor
```

### 4. Polymorphism

Both `Patient` and `Doctor` implement the `get_role()` method according to their respective roles.

### 5. Composition

The `Hospital` class acts as the central coordinator and manages collections of patients, doctors, wards, appointments, and bills.

### 6. Dataclasses

`Appointment` and `BillItem` use Python's `@dataclass` for concise data-oriented classes.

### 7. Exception Handling

The project contains a custom exception hierarchy for handling invalid input, missing records, unavailable doctors, unavailable beds, appointment conflicts, and invalid appointment states.

---

## 🏗️ System Architecture

```text
                         Hospital
                            │
          ┌─────────────────┼─────────────────┐
          │                 │                 │
          ▼                 ▼                 ▼
       Patient           Doctor             Ward
          │                 │
          └────────┐   ┌────┘
                   ▼   ▼
                Appointment
                     │
                     ▼
                   Bill
                     │
                     ▼
                 BillItem
```

---

## 📦 Main Classes

| Class         | Responsibility                                                    |
| ------------- | ----------------------------------------------------------------- |
| `Person`      | Abstract base class for people in the hospital                    |
| `Patient`     | Stores patient information, admission status, history and records |
| `Doctor`      | Stores doctor information, department and appointment schedule    |
| `Ward`        | Manages total and occupied beds                                   |
| `Appointment` | Represents a patient-doctor appointment                           |
| `BillItem`    | Represents an individual billing item                             |
| `Bill`        | Manages billing, payments and outstanding balance                 |
| `Hospital`    | Central coordinator for the complete system                       |
| `HospitalCLI` | Provides the menu-driven command-line interface                   |

---

## 🔗 Database Schema

The schema represents the main entities and relationships used by the application.

### Main Relationships

```text
Patient  1 ───────< Appointment >─────── 1 Doctor

Ward     1 ───────< Patient

Patient  1 ───────< Bill

Bill     1 ───────< BillItem
```

### Schema Diagram

<img src="./schema.png" alt="Hospital Management System Database Schema" width="100%">

---

## ⚙️ Main Features

### 👤 Patient Management

* Register new patients
* Store name, age, gender and phone
* Store blood group
* Track admission status
* Maintain medical history
* View patient details
* Track appointments and outstanding bills

### 👨‍⚕️ Doctor Management

* Register doctors
* Assign departments
* Set consultation fees
* Check doctor availability
* Maintain appointment schedules

### 🏥 Ward Management

* Add hospital wards
* Define total bed capacity
* Track occupied beds
* Calculate available beds
* Prevent admission when no beds are available

### 📅 Appointment Management

* Book appointments
* Validate appointment time
* Check doctor availability
* Prevent appointment conflicts
* Complete appointments
* Add diagnosis
* Cancel scheduled appointments

### 💳 Billing System

* Create bills for patients
* Add multiple bill items
* Calculate total amount
* Record payments
* Calculate remaining balance
* Automatically add consultation charges after appointment completion

---

## 🔄 Appointment Workflow

```text
Book Appointment
       │
       ▼
Check Patient
       │
       ▼
Check Doctor
       │
       ▼
Check Time Slot
       │
       ▼
Create Appointment
       │
       ▼
Complete Appointment
       │
       ├── Add Diagnosis
       ├── Update Medical History
       ├── Free Doctor Slot
       └── Create/Update Bill
```

---

## 💰 Billing Workflow

```text
Appointment Completed
        │
        ▼
Create / Get Bill
        │
        ▼
Add Consultation Fee
        │
        ▼
Add Bill Items
        │
        ▼
Calculate Total
        │
        ▼
Make Payment
        │
        ▼
Calculate Remaining Balance
```

---

## ⚠️ Custom Exception Handling

The project uses a custom exception hierarchy:

```text
HospitalError
│
├── InvalidInputError
├── PatientNotFoundError
├── DoctorNotFoundError
├── DoctorUnavailableError
├── AppointmentNotFoundError
├── AppointmentConflictError
├── InvalidAppointmentStateError
└── BedUnavailableError
```

This makes the system easier to maintain and allows different hospital-related errors to be handled appropriately.

---

## 🖥️ CLI Menu

The application provides a menu-driven interface:

```text
==================== MAIN MENU ====================

 1. Register Patient
 2. Register Doctor
 3. List Doctors
 4. Book Appointment
 5. Complete Appointment (add diagnosis + bill)
 6. Cancel Appointment
 7. Admit Patient
 8. Discharge Patient
 9. View Patient Details
10. Pay Bill
11. Hospital Statistics
 0. Exit

====================================================
```

---

## 🚀 How to Run

### Prerequisites

* Python 3.9+
* Jupyter Notebook / Google Colab / Python interpreter

The project uses Python's standard library, so no external package installation is required.

### Run with Python

If the Python file is available:

```bash
python Hospital_Management_System.py
```

### Run the Notebook

Open:

```text
Hospital_Management_System.ipynb
```

in Jupyter Notebook, JupyterLab, or Google Colab and run the cells.

---

## 🗂️ Project Structure

```text
Hospital_Management_System/
│
├── Hospital_Management_System.ipynb
├── Readme.md
└── schema.png
```

---

## 📊 Hospital Statistics

The system can display:

* Total patients
* Total doctors
* Currently admitted patients
* Scheduled appointments
* Total beds
* Available beds

---

## 🔑 ID Generation

The system automatically generates short unique IDs using Python's `uuid` module.

Example:

```text
Patient ID       → A81F92BC
Doctor ID        → 4D72F1A9
Appointment ID   → C91B83E2
Bill ID          → F72A10BC
```

---

## 🎯 Learning Objectives

This project was developed to understand how OOP concepts can be applied to a practical real-world system.

Through this project, the following concepts are demonstrated:

* Classes and Objects
* Constructors
* Encapsulation
* Abstraction
* Inheritance
* Polymorphism
* Composition
* Properties and Setters
* Dataclasses
* Enumerations
* Custom Exceptions
* Type Hints
* Collections
* CLI-based application design

---

## 📝 Note

This project is primarily an **Object-Oriented Programming implementation**. The application currently manages its data in memory using Python objects and collections rather than connecting to a persistent SQL/NoSQL database.

The schema diagram is provided to represent how the application's entities and relationships can be modeled in a database design.

---

## 👨‍💻 Author

**Aditya Kumar Singh**

---

## ⭐ If you found this project useful

Feel free to explore the code, improve the system, and experiment with additional hospital management features.
