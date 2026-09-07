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

