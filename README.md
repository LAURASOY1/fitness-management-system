# Gym Management System

## Overview

The Gym Management System is a Command-Line Interface (CLI) application designed to manage various aspects of a gym, including members, trainers, fitness classes, schedules, attendance, and payments. The application is built using Python and SQLAlchemy for Object-Relational Mapping (ORM), making it easy to interact with the underlying SQLite database.

## Features

- **Member Management**: Add, update, delete, and list gym members.
- **Trainer Management**: Add, update, delete, and list trainers.
- **Fitness Class Management**: Add, update, delete, and list fitness classes.
- **Schedule Management**: Manage the schedules for fitness classes.
- **Attendance Tracking**: Track attendance for fitness classes.
- **Payment Management**: Record and manage payments made by members.

## Project Structure

```
.
└── lib
    ├── models
    │   ├── __init__.py
    │   ├── member.py
    │   ├── trainer.py
    │   ├── fitness_class.py
    │   ├── schedule.py
    │   ├── attendance.py
    │   └── payment.py
    ├── cli.py
    ├── fitness_management.db
    ├── helpers.py
├── Pipfile
├── Pipfile.lock
├── pytest.ini
├── README.md
```

## Installation

1. **Clone the Repository**

   ```sh
   git clone git@github.com:LAURASOY1/fitness-management-system.git
   cd gym-management-system
   ```

2. **Install Dependencies**

   Ensure you have `pipenv` installed. If not, install it using `pip`:

   ```sh
   pip install pipenv
   ```

   Then install the project dependencies:

   ```sh
   pipenv install
   ```

3. **Set Up the Database**

   Initialize the database:

   ```sh
   pipenv run python -m lib.models
   ```

## Usage

Activate the pipenv shell:

```sh
pipenv shell
```

Run the CLI application:

```sh
python lib/cli.py
```

You will be prompted with the following options:

```sh
Please select an option:
0. Exit the program
1. List all members
2. Find member by name
3. Find member by id
4. Create member
5. Update member
6. Delete member
7. List all trainers
8. Find trainer by name
9. Find trainer by id
10. Create trainer
11. Update trainer
12. Delete trainer
13. List all attendance records
14. Add attendance record
15. List all fitness classes
16. Add fitness class
17. List all payments
18. Add payment
> 3
Enter the member's id: 3
Traceback (most recent call last):
  File "lib/cli.py", line 90, in <module>
    main()
  File "lib/cli.py", line 55, in main
    find_member_by_id()
  File "/home/laura/Downloads/fitness-management-system-Main/lib/helpers.py", line 28, in find_member_by_id
    member = Member.find_by_id(member_id)
  File "/home/laura/Downloads/fitness-management-system-Main/lib/models/member.py", line 48, in find_by_id
    cursor = conn.execute('SELECT * FROM members WHERE member_id = ?', (member_id,))
sqlite3.OperationalError: no such table: members
laura@laura-HP-EliteBook-x360-1030-G2:~/Downloads/fitness-management-system-Main$ sqlite3 fitness_management.db
SQLite version 3.31.1 2020-01-27 19:55:54
Enter ".help" for usage hints.
sqlite> .tables
attendance       members          trainers       
fitness_classes  payments       
sqlite> .quit
laura@laura-HP-EliteBook-x360-1030-G2:~/Downloads/fitness-management-system-Main$ git remote add origin git@github.com:LAURASOY1/fitness-management-system.git
fatal: not a git repository (or any of the parent directories): .git
laura@laura-HP-EliteBook-x360-1030-G2:~/Downloads/fitness-management-system-Main$ git init
Initialized empty Git repository in /home/laura/Downloads/fitness-management-system-Main/.git/
laura@laura-HP-EliteBook-x360-1030-G2:~/Downloads/fitness-management-system-Main$ git commit -am "fitness"
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Pipfile
        Pipfile.lock
        README.md
        fitness_management.db
        lib/

nothing added to commit but untracked files present (use "git add" to track)
laura@laura-HP-EliteBook-x360-1030-G2:~/Downloads/fitness-management-system-Main$ git add .
laura@laura-HP-EliteBook-x360-1030-G2:~/Downloads/fitness-management-system-Main$ git commit -m "fitness"
[master (root-commit) 0d1668e] fitness
 30 files changed, 957 insertions(+)
 create mode 100644 Pipfile
 create mode 100644 Pipfile.lock
 create mode 100644 README.md
 create mode 100644 fitness_management.db
 create mode 100644 lib/__pycache__/helpers.cpython-310.pyc
 create mode 100644 lib/__pycache__/helpers.cpython-38.pyc
 create mode 100644 lib/cli.py
 create mode 100644 lib/create_tables.py
 create mode 100644 lib/fitness_management.db
 create mode 100644 lib/helpers.py
 create mode 100644 lib/models/__pycache__/_init_.cpython-310.pyc
 create mode 100644 lib/models/__pycache__/_init_.cpython-38.pyc
 create mode 100644 lib/models/__pycache__/attendance.cpython-310.pyc
 create mode 100644 lib/models/__pycache__/attendance.cpython-38.pyc
 create mode 100644 lib/models/__pycache__/fitness_class.cpython-310.pyc
 create mode 100644 lib/models/__pycache__/fitness_class.cpython-38.pyc
 create mode 100644 lib/models/__pycache__/member.cpython-310.pyc
 create mode 100644 lib/models/__pycache__/member.cpython-38.pyc
 create mode 100644 lib/models/__pycache__/payment.cpython-310.pyc
 create mode 100644 lib/models/__pycache__/payment.cpython-38.pyc
 create mode 100644 lib/models/__pycache__/trainer.cpython-310.pyc
 create mode 100644 lib/models/__pycache__/trainer.cpython-38.pyc
 create mode 100644 lib/models/_init_.py
 create mode 100644 lib/models/attendance.py
 create mode 100644 lib/models/fitness_class.py
 create mode 100644 lib/models/member.py
 create mode 100644 lib/models/payment.py
 create mode 100644 lib/models/schedule.py
 create mode 100644 lib/models/trainer.py
 create mode 100644 lib/seed.py
laura@laura-HP-EliteBook-x360-1030-G2:~/Downloads/fitness-management-system-Main$ git branch -M main
laura@laura-HP-EliteBook-x360-1030-G2:~/Downloads/fitness-management-system-Main$ git remote add origin git@github.com:LAURASOY1/fitness-management-system.git
laura@laura-HP-EliteBook-x360-1030-G2:~/Downloads/fitness-management-system-Main$ git push -u origin main
Enumerating objects: 35, done.
Counting objects: 100% (35/35), done.
Delta compression using up to 4 threads
Compressing objects: 100% (34/34), done.
Writing objects: 100% (35/35), 23.15 KiB | 878.00 KiB/s, done.
Total 35 (delta 9), reused 0 (delta 0)
remote: Resolving deltas: 100% (9/9), done.
To github.com:LAURASOY1/fitness-management-system.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
laura@laura-HP-EliteBook-x360-1030-G2:~/Downloads/fitness-management-system-Main$ python lib/cli.py
Please select an option:
0. Exit the program
1. List all members
2. Find member by name
3. Find member by id
4. Create member
5. Update member
6. Delete member
7. List all trainers
8. Find trainer by name
9. Find trainer by id
10. Create trainer
11. Update trainer
12. Delete trainer
13. List all attendance records
14. Add attendance record
15. List all fitness classes
16. Add fitness class
17. List all payments
18. Add payment
```

## Example Commands

### Members

- **List all members**

  ```sh
  python lib/cli.py list_members
  ```

- **Find member by name**

  ```sh
  python lib/cli.py find_member_by_name "John Doe"
  ```

- **Create a member**

  ```sh
  python lib/cli.py create_member "John Doe" "Premium"
  ```

### Trainers

- **List all trainers**

  ```sh
  python lib/cli.py list_trainers
  ```

- **Create a trainer**

  ```sh
  python lib/cli.py create_trainer "Jane Smith" "Yoga"
  ```

### Fitness Classes

- **List all fitness classes**

  ```sh
  python lib/cli.py list_fitness_classes
  ```

- **Create a fitness class**

  ```sh
  python lib/cli.py create_fitness_class "Morning Yoga" 1
  ```

### Schedules

- **List all schedules**

  ```sh
  python lib/cli.py list_schedules
  ```

- **Create a schedule**

  ```sh
  python lib/cli.py create_schedule 1 "2024-06-10"
  ```

### Payments

- **List all payments**

  ```sh
  python lib/cli.py list_payments
  ```

- **Create a payment**

  ```sh
  python lib/cli.py create_payment 1 100 "2024-06-10"
  ```

## Running Tests

To run the tests, use the following command:

```sh
pipenv run pytest
```

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
