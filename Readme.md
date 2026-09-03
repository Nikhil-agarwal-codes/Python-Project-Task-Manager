# Task Manager (Python Tkinter Desktop App)

## Overview

This project is a simple desktop-based Task Manager built using Python's Tkinter library. The idea behind the app was to create a small tool that helps manage day-to-day tasks without depending on mobile apps or online platforms. The program allows users to add tasks, update them whenever required, search through the list, and delete tasks they no longer need.

The goal was to learn the basics of GUI development, event-driven logic, and handling multiple UI components inside a single application window.

## Features

- Add new tasks using a clean input field
- Update any selected task
- Delete tasks from the list
- Search/filter tasks instantly
- Scrollable task list for easy navigation
- Simple and beginner-friendly codebase

## Technologies / Tools Used

- Python 3.x
- Tkinter (default Python GUI framework)
- Basic message dialogs from `tkinter.messagebox`

## How to Install & Run the Project

### 1. Requirements

Make sure Python 3.x is installed on your system. Tkinter usually comes bundled with Python, so no extra installation is required.

### 2. Running the Program

1. Download or copy the project file (`b.py`).
2. Open a terminal or command prompt in the folder where the file is located.
3. Run the following command:

   ```bash
   python b.py
   ```

The Task Manager window should appear on your screen immediately.

## How to Test the Application

Here's a quick way to verify everything works as expected:

### 1. Adding a Task

- Type something in the "Enter Task" box
- Click **Add Task**
- The task should appear instantly in the list

### 2. Searching for a Task

- Use the search box to filter items
- The list updates automatically as you type
- Clear the search bar to see all tasks again

### 3. Updating a Task

- Select a task from the list
- Enter the new version of the task in the input box
- Click **Update Task** and check if it changes correctly

### 4. Deleting a Task

- Select any task
- Hit **Delete Task**
- Verify that it disappears from the list

### 5. Error Handling

Try some invalid actions like:

- Pressing Update without selecting a task
- Adding an empty task
- Deleting without selecting a task

You should see proper warning dialogs.






