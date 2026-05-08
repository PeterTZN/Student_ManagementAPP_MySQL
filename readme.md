# Student Management System 🎓

A desktop application built with Python and PyQt6 for managing student records simply and efficiently, powered by a MySQL database backend.

---

## Features

- Add new student records with name, course and mobile number
- Edit existing student records
- Delete student records with confirmation dialog
- Search for students by name
- Data stored securely in a MySQL database
- Clean interface with toolbar, menu bar and dynamic status bar
- About dialog with app information

---

## Requirements

- Python 3.x
- PyQt6
- MySQL Server
- mysql-connector-python

---

## Installation

1. **Clone or download the repository:**
   ```
   git clone https://github.com/yourusername/student-management-system.git
   ```

2. **Navigate to the project directory:**
   ```
   cd student-management-system
   ```

3. **Install dependencies:**
   ```
   pip install PyQt6 mysql-connector-python
   ```

4. **Set up your MySQL database** (see Database Setup below)

5. **Run the application:**
   ```
   python main.py
   ```

---

## Database Setup

1. **Make sure MySQL Server is running on your machine**

2. **Create the database and table** by running the following in MySQL:

```sql
CREATE DATABASE school;

USE school;

CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255),
    course VARCHAR(255),
    mobile VARCHAR(255)
);
```

3. **Update the database credentials** in the `DatabaseConnection` class inside `main.py` if needed:

```python
class DatabaseConnection:
    def __init__(self, host="localhost", user="root",
                 password="yourpassword", database="school"):
```

---

## How To Use

| Action | How |
|---|---|
| Add a student | File → Add Student or toolbar icon |
| Search for a student | Edit → Search or toolbar icon |
| Edit a student | Click a row → Edit Record button in status bar |
| Delete a student | Click a row → Delete Record button in status bar |
| About | Help → About |

---

## Project Structure

```
student-management-system/
│
├── main.py               # Main application file
├── icons/
│   ├── add.png           # Add student toolbar icon
│   └── search.png        # Search toolbar icon
└── README.md             # This file
```

---

## Key Differences From SQLite Version

| Feature | Previous Version | This Version |
|---|---|---|
| Database | SQLite (local file) | MySQL (server) |
| Connection | sqlite3 (built-in) | mysql-connector-python |
| Placeholders | `?` | `%s` |
| Setup required | None | MySQL Server install |

---

## Built With

- [Python 3](https://www.python.org/) - Programming language
- [PyQt6](https://pypi.org/project/PyQt6/) - GUI framework
- [MySQL](https://www.mysql.com/) - Database server
- [mysql-connector-python](https://pypi.org/project/mysql-connector-python/) - MySQL driver

---

## Author

Built by Peter Thomson

---

## License

This project is open source and available under the [MIT License](LICENSE).