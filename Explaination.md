# Task Manager GUI — Code Explanation
 
This document walks through `b.py`, a desktop **Task Manager** application built with Python's `tkinter` library. The app lets a user add, search, update, and delete tasks in a simple dark-themed window.
 
---
 
## 1. Imports
 
```python
import tkinter as tk
from tkinter import messagebox
```
 
- `tkinter` is Python's built-in GUI toolkit — it provides windows, buttons, text fields, etc.
- `messagebox` is a sub-module used to pop up alert/warning/error dialog boxes (e.g., "Please enter a task").
---
 
## 2. The `TaskManagerGUI` Class
 
The whole application is wrapped in a class called `TaskManagerGUI`. This is a common pattern for tkinter apps: it keeps the window (`root`), the widgets, and the app's logic organized together instead of using scattered global variables.
 
### 2.1 The Constructor (`__init__`)
 
```python
def __init__(self, root):
    self.root = root
    self.root.title("Task Manager")
    self.root.geometry("430x560")
```
 
- `root` is the main tkinter window, passed in from outside the class.
- `self.root` stores a reference to it so other methods in the class can use it later.
- `.title()` sets the window's title bar text.
- `.geometry("430x560")` fixes the window size to 430 pixels wide by 560 pixels tall.

