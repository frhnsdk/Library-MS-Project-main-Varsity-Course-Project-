# Library Management System

A desktop application for managing library books, borrowing, and returns, built with Python and Tkinter.

## Features

- Add new books to the library
- Issue books to students
- Return books
- View all books
- Search for books
- View book holders (borrow records)
- Update and delete book records
- Limit of 3 books per student

## Requirements

- Python 3.x
- `pymysql` package
- MySQL server (with a database named `library_management`)

## Setup

1. **Clone the repository**  
	```
	git clone <repo-url>
	cd Library-MS-Project-main
	```

2. **Install dependencies**  
	```
	pip install pymysql
	```

3. **Configure MySQL credentials**  
	Edit `credentials.py` with your MySQL server details:
	```python
	host = 'localhost'
	user = 'root'
	password = 'yourpassword'
	database = 'library_management'
	```

4. **Create the required database and tables**  
	Use the following SQL to set up your database:
	```sql
	CREATE DATABASE library_management;
	USE library_management;

	CREATE TABLE book_list (
		 book_id INT PRIMARY KEY,
		 book_name VARCHAR(255),
		 author VARCHAR(255),
		 edition VARCHAR(50),
		 price FLOAT,
		 qty INT
	);

	CREATE TABLE borrow_record (
		 book_id INT,
		 book_name VARCHAR(255),
		 stu_roll VARCHAR(50),
		 stu_name VARCHAR(255),
		 course VARCHAR(100),
		 subject VARCHAR(100),
		 issue_date DATE,
		 return_date DATE
	);
	```

## How to Run

1. **Start the application**
	```
	python main.py
	```

2. **Use the GUI:**
	- **Add Book:** Enter book details and add to library.
	- **Issue Book:** Enter book and student details to issue a book.
	- **Return Book:** Enter student roll number to return a book.
	- **All Books:** View all books in the library.
	- **Search Book:** Search for a book by name.
	- **Book Holders:** View all students who have borrowed books.
	- **Clear Screen:** Reset the current view.
	- **Exit:** Close the application.

## Notes

- Each student can borrow up to 3 books.
- You cannot delete a book if it is currently borrowed.
- All operations are performed via the graphical interface.

# Customization

- Colors and fonts can be changed in `customs.py`.
- Database credentials are set in `credentials.py`.

## Author

Developed by Farhan Sadik and varsity team mates
