# Simulation-Game

A simple C-based **Student Management System** with role-based access control and file-based storage.

## Features

- User login with up to 3 attempts
- Role-based menus:
  - **ADMIN**: add, display, search, update, delete student records
  - **STAFF**: add, display, search student records
  - **GUEST / USER**: display and search student records (read-only)
- Persistent data using text files

## Project Structure

- `project.c` - main source code
- `students.txt` - student records data
- `credentials (1).txt` - sample login credentials

## Requirements

- GCC or Clang compiler

## Build and Run

From the repository root:

```bash
gcc -Wall -Wextra -Werror -o simulation project.c
```

The program reads credentials from `credentials.txt`.  
This repository includes `credentials (1).txt`, so create the expected file before running:

```bash
cp "credentials (1).txt" credentials.txt
./simulation
```

## Credentials File Format

Each line in `credentials.txt` should be:

```text
username password ROLE
```

Example roles used by the program:
- `ADMIN`
- `STAFF`
- `GUEST`
- `USER`

## Student Data Format

Each line in `students.txt` should be:

```text
roll_number name marks
```

The current parser reads name as a single space-separated token, so use names without spaces (for example, `Alice` or `Alice_Smith`).

Example:

```text
101 Alice 88.50
```

## Notes

- If `credentials.txt` is missing, login will fail with an error message.
