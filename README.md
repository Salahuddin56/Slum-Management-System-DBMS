# Slum-Management-System-DBMS
# 🏘️ Automated Centralized Slum Management Database System

> **Database Systems Project**
> Department of Computer Science and Engineering, Military Institute of Science and Technology (MIST), Dhaka-1216, Bangladesh

![Oracle](https://img.shields.io/badge/Oracle-SQL%20Developer%2011g-red?logo=oracle)
![Laravel](https://img.shields.io/badge/Laravel-5.8-orange?logo=laravel)
![Windows](https://img.shields.io/badge/Windows-10-blue?logo=windows)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![draw.io](https://img.shields.io/badge/Diagrams-draw.io-yellow)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Team](#team)
- [System Diagrams](#system-diagrams)
- [Database Design](#database-design)
- [System Features](#system-features)
- [Modules](#modules)
- [Installation](#installation)
- [Usage](#usage)
- [Limitations & Future Work](#limitations--future-work)
- [References](#references)

---

## Overview

The **Slum Management System** is an automated centralized database designed to improve the quality of life of slum dwellers and aid government bodies and NGOs in regulating slum areas across urban Bangladesh. The system was developed following field visits to the **Bhashantek** and **Korail** slums of Dhaka, with guidance from **BRAC** representatives.

The database covers five core aspects of slum life:

| Sector | Description |
|---|---|
| 🏥 Health & Sanitation | Patient records, treatments, medical centre management |
| 🏠 Housing | House records, rent collection, deposition tracking |
| 💰 Loan | Micro-finance loan management and installment tracking |
| 🏦 Savings | Savings accounts for those without bank access |
| 📚 Education | Student records, institutions, educational staff |

The system is designed to serve NGOs, government organizations, international aid bodies, healthcare providers, and microfinance institutions working with slum communities.

---

## Team

| Name | Email |
|---|---|
| Afia Anjum Ananya | afia.anjum70@gmail.com |
| Salahuddin Elias Khan | salahuddinace56@gmail.com |
| Samiha Raisa Zaman | samiharaisa031@gmail.com |
| Neamat Al Sarah | neamatsarah@gmail.com |
| Tamanna Tasnim Tithy | tamannatasnim@gmail.com |
| Nazma Nawal Parisa | nawalparisa@gmail.com |

**Institution:** Military Institute of Science and Technology (MIST), Dhaka, Bangladesh

---

## System Diagrams

### 📌 ER Diagram
The Entity-Relationship Diagram covers all major entities including Slum-Dweller, Employee, Donor, Housing, Loan, Student, Savings Account, ICT Centre, Institution, and more.

🔗 **[View ER Diagram on Google Drive](https://drive.google.com/file/d/1ys9eOv-ecUSo1xJIH5PNHDl3ucNf18Or/view?usp=sharing)**

---

### 📌 Schema Diagram
The Schema Diagram maps out all tables, primary keys, foreign keys, and relationships across the full database.

🔗 **[View Schema Diagram on Google Drive](https://drive.google.com/file/d/1lJk2BR9SYUos7uw5oq-P7cRdjGgopNTL/view?usp=drive_link)**

---

## Database Design

The database is split into two major parts:

### 🔐 Administrator Side
Handles organizational management:
- `Donor` — donor information and contribution history
- `Transaction` — all financial transactions and withdrawals
- `Project Info` — project details, progress, and remaining budget
- `Project Withdrawal` — fund withdrawals per project
- `Employee` — staff records (Rent Collector, Loan Employee, Data Collector, ICT Employee, Educational Staff, Health Worker, Distributor)
- `Inventory` — Medicine, Food, Furniture & Electronics, Educational Items

### 👤 User Side
Handles slum dweller services:
- `Slum-Dweller` — personal records (NID, Khana No, Ration ID, occupation, income)
- `Housing` — house assignments, rent, deposition
- `Loan + Customer Payment Info` — loan details and installment tracking
- `Savings Account + Transaction Account` — savings management
- `Student + Institution` — education records
- `Patient + Treatment + Test` — health records
- `ICT Centre` — digital literacy centre management

### Key Tables
Person ──► Slum-Dweller ──► Housing
──► Loan ──► Customer Payment Info
──► Savings Account ──► Transaction Account
──► Student ──► Institution
Employee ──► Health Worker ──► Medical Centre ──► Treatment
──► Loan Employee ──► Gives (Loan)
──► Rent Collector
──► ICT Employee ──► ICT Centre
──► Educational Staff
──► Data Collector
──► Distributor ──► Distribution ──► Inventory
Donor ──► Transaction ──► Project Info
──► Storage Place ──► Inventory

---

## System Features

| Feature | Access |
|---|---|
| User Registration & Login | All Users |
| Admin Login | Admin Only |
| Insert / Delete / Update records | Admin Only |
| Search by NID, Name, ID | Admin + Relevant Employee |
| View Project Information | All Logged-in Users |
| Inventory Management | Admin Only |
| Donor Management | Admin Only |
| Housing & Rent Collection | Admin + Rent Collector |
| Loan & Savings Management | Admin + Loan Employee |
| Health Records Management | Admin + Health Worker |
| Education Records | Admin + Educational Staff |

> ⚠️ **Access Restriction:** No user (including admin) can insert, delete, or update any data between **5:00 PM and 8:00 AM** or on **weekends**.

---

## Modules

### 1. 🏥 Health & Sanitation
- Search patient by NID to view treatment history, referral doctor, follow-up date, and fees
- Search by doctor's name to view all patients under them
- Health workers can add/update patient and treatment records
- Covers: `Patient`, `Treatment`, `Test`, `Pathology`, `Medical Centre`, `Service`

### 2. 🏠 Housing
- Rent collector views and updates rent records per house ID
- Displays list of houses with outstanding rent
- Covers: `Home`, `Housing`, `Rent Collector`

### 3. 💰 Loan
- Microfinance system for slum dwellers without bank access
- Loan employee manages loan sanctioning, installments, and payment tracking
- Search by NID shows remaining loan, installments left, and next payment date
- Covers: `Loan`, `Gives`, `Customer Payment Info`, `Loan Employee`

### 4. 🏦 Savings
- For slum dwellers without formal bank access
- Loan employee manages deposits, account opening, and savings tracking
- Search by NID shows savings ID and total amount deposited
- Covers: `Saving Account`, `Transaction Account`, `Borrows`, `Collects In`

### 5. 📚 Education
- Tracks student enrollment, exam results, and institutional affiliation
- Educational staff manage records within working hours only
- Covers: `Student`, `Institution`, `Educational Staff`, `Study At`

### 6. 📦 Inventory (Admin Only)
Four inventory categories managed exclusively by admin:
- `Medicine` — name, type, dose, manufacture/expiry date, subsidized price
- `Food` — name, type, fresh-till date, amount
- `Furniture & Electronics` — name, brand, price, material type
- `Educational Items` — name, class, branch, type, amount

---

## Installation

### System Requirements

| Software | Version |
|---|---|
| OS | Windows 10 |
| Database | Oracle SQL Developer 11g |
| Backend Framework | Laravel 5.8 |
| PHP | Compatible with Laravel 5.8 |
| Diagram Tool | draw.io |

### Setup Steps

```bash
# Clone the repository
git clone https://github.com/your-username/slum-management-system.git
cd slum-management-system

# Install PHP dependencies
composer install

# Copy environment file
cp .env.example .env

# Configure your Oracle DB credentials in .env
DB_CONNECTION=oracle
DB_HOST=127.0.0.1
DB_PORT=1521
DB_DATABASE=slumdb
DB_USERNAME=your_username
DB_PASSWORD=your_password

# Generate application key
php artisan key:generate

# Run migrations (if available)
php artisan migrate

# Start the local server
php artisan serve
```

Then open your browser and go to `http://localhost:8000`

---

## Usage

### Login Types

**Super Admin**
- Can create and manage admin accounts
- Has full access to all tables and modules

**Admin**
- Full read/write access to all database tables
- Manages donors, transactions, projects, inventory, and employees

**User (Employee)**
- Registers and logs in with their role
- Access restricted to their relevant module only
- Cannot perform any operations outside working hours (5 PM – 8 AM) or on weekends

### Example Workflows

**Searching a loan record:**
> Loan Employee → enters NID → views loan ID, amount remaining, installments left, next payment date

**Admitting a patient:**
> Health Worker → enters patient NID, symptoms → data stored in `Patient` table → doctor logs treatment in `Treatment` table

**Adding a donor:**
> Admin → Donor page → enters name, amount, date → stored in `Donor` and `Transaction` tables

---

## Limitations & Future Work

1. **Rural slums not covered** — The system was designed based on field visits to urban slums (Bhashantek, Korail, Dhaka). Rural slum lifestyles differ significantly and are not fully accommodated.

2. **Homeless population** — Individuals without a fixed address (floating population) are not represented in the current schema.

3. **Mobile accessibility** — The current system is desktop-based; a mobile-friendly interface would greatly improve field worker usability.

4. **Real-time reporting** — Future versions should include dashboards and analytics for NGOs and government bodies to monitor slum conditions in real time.

5. **Integration with national ID system** — Linking with Bangladesh's national NID database would reduce data duplication and improve verification.

6. **Offline support** — Field workers in slums often have limited connectivity; offline data entry with sync capability would be a valuable addition.

---

## References

1. Angeles G, et al. *The 2005 census and mapping of slums in Bangladesh.* International Journal of Health Geographics. 2009;8(1):32.
2. Wikipedia. *Slum.* https://en.wikipedia.org/wiki/Slum. 2019.
3. Ooi GL, Phua KH. *Urbanization and slum formation.* Journal of Urban Health. 2007;84(1):27–34.
4. Werlin H. *The slum upgrading myth.* Urban Studies. 1999;36(9):1523–1534.
5. Madon S, Sahay S. *An information-based model of NGO mediation for the empowerment of slum dwellers in Bangalore.* The Information Society. 2002;18(1):13–19.
6. Minnery J, et al. *Slum upgrading and urban governance: Case studies in three South East Asian cities.* Habitat International. 2013;39:162–169.
7. Habib E. *The role of government and NGOs in slum development: the case of Dhaka City.* Development in Practice. 2009;19(2):259–265.
8. Afsana K, Wahid SS. *Health care for poor people in the urban slums of Bangladesh.* The Lancet. 2013;382(9910):2049–2051.
9. Sarkar M. *Personal hygiene among primary school children living in a slum of Kolkata, India.* Journal of Preventive Medicine and Hygiene. 2013;54(3):153.
10. Mugisha F. *School enrollment among urban non-slum, slum and rural children in Kenya.* International Journal of Educational Development. 2006;26(5):471–482.
11. Fernandez A, Mondkar J, Mathai S. *Urban slum-specific issues in neonatal survival.* Indian Pediatrics. 2003;40(12):1161–1166.

---

## Acknowledgements

Special thanks to **BRAC** representatives for their guidance during field visits to Bhashantek and Korail slums, Dhaka, which shaped the design and scope of this system.

---

*Department of Computer Science and Engineering | Military Institute of Science and Technology (MIST) | Dhaka-1216, Bangladesh*
