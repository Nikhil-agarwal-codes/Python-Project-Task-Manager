```python
import tkinter as tk
from tkinter import messagebox

class TaskManagerGUI:
    def __init__(self, root):
        self.root = root
        self.root.title("Task Manager")
        self.root.geometry("430x560")
# list to store tasks
        self.all_tasks = []

        # ------ color palette ------
        background = "#1e1e1e"
        text_color = "#ffffff"
        entry_color = "#2c2c2c"
        list_color = "#262626"

        green_btn = "#4CAF50"
        blue_btn = "#2196F3"
        red_btn = "#f44336"

        self.root.config(bg=background)

 # ------ header ------
        tk.Label(
            root,
            text="Task Manager",
            font=("Arial", 20, "bold"),
            bg=background,
            fg=text_color
        ).pack(pady=10)

        # ------ search bar ------
        tk.Label(
            root,
            text="Search Task:",
            font=("Arial", 12),
            bg=background,
            fg=text_color
        ).pack()
 self.search_entry = tk.Entry(
            root,
            width=30,
            font=("Arial", 12),
            bg=entry_color,
            fg=text_color,
            insertbackground=text_color
        )
        self.search_entry.pack(pady=4)
        self.search_entry.bind("<KeyRelease>", self.filter_tasks)

        # ------ task input field ------
        tk.Label(
            root,
            text="Enter Task:",
            font=("Arial", 12),
            bg=background,
            fg=text_color
        ).pack()
