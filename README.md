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
