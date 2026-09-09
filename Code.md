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
# ------ buttons row ------
        btn_container = tk.Frame(root, bg=background)
        btn_container.pack(pady=10)

        tk.Button(
            btn_container,
            text="Add Task",
            width=12,
            bg=green_btn,
            fg="white",
            command=self.add_task
        ).grid(row=0, column=0, padx=5)

        tk.Button(
            btn_container,
            text="Update Task",
            width=12,
            bg=blue_btn,
            fg="white",
            command=self.update_task
        ).grid(row=0, column=1, padx=5)

        tk.Button(
            btn_container,
            text="Delete Task",
            width=12,
            bg=red_btn,
            fg="white",
            command=self.delete_task
        ).grid(row=0, column=2, padx=5)
 # ------ listbox with scrollbar ------
        list_frame = tk.Frame(root, bg=background)
        list_frame.pack(pady=10)

        self.listbox = tk.Listbox(
            list_frame,
            width=50,
            height=15,
            font=("Arial", 11),
            bg=list_color,
            fg=text_color,
            selectbackground="#444"
        )
        self.listbox.pack(side=tk.LEFT)

        scroll = tk.Scrollbar(list_frame, command=self.listbox.yview)
        scroll.pack(side=tk.RIGHT, fill=tk.Y)

        self.listbox.config(yscrollcommand=scroll.set)
