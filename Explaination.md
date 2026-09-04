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

```python
self.all_tasks = []
```
 
- This list is the app's **data store** — every task the user adds lives here in memory. Nothing is saved to a file or database, so tasks disappear when the app closes.
### 2.2 Color Palette
 
```python
background = "#1e1e1e"
text_color = "#ffffff"
entry_color = "#2c2c2c"
list_color = "#262626"
 
green_btn = "#4CAF50"
blue_btn = "#2196F3"
red_btn = "#f44336"
```
 
These are just hex color codes stored in local variables so the dark theme is defined once and reused consistently across all widgets (background near-black, white text, colored buttons for different actions). 
- `root` is the main tkinter window, passed in from outside the class.
- `self.root` stores a reference to it so other methods in the class can use it later.
- `.title()` sets the window's title bar text.
- `.geometry("430x560")` fixes the window size to 430 pixels wide by 560 pixels tall.

```python
self.root.config(bg=background)
```
 
Applies the dark background color to the main window itself.
 
---
 
## 3. Building the Interface (Widgets)
 
Widgets are created and immediately "packed" onto the window using `.pack()`, which stacks them vertically by default.
 
### 3.1 Header Label
 
```python
tk.Label(root, text="Task Manager", font=("Arial", 20, "bold"), bg=background, fg=text_color).pack(pady=10)
```
 
A large bold title at the top of the window. `pady=10` adds 10 pixels of vertical spacing around it.
