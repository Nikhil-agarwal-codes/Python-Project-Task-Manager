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

        self.task_entry = tk.Entry(
            root,
            width=30,
            font=("Arial", 12),
            bg=entry_color,
            fg=text_color,
            insertbackground=text_color
        )
        self.task_entry.pack(pady=5)

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

    # --- helper to refresh list display ---
    def refresh_listbox(self, data):
        self.listbox.delete(0, tk.END)
        for entry in data:
            self.listbox.insert(tk.END, entry)

    # --- search logic ---
    def filter_tasks(self, event=None):
        word = self.search_entry.get().lower().strip()

        if not word:
            self.refresh_listbox(self.all_tasks)
            return

        filtered = [t for t in self.all_tasks if word in t.lower()]
        self.refresh_listbox(filtered)

    # --- add new task ---
    def add_task(self):
        new_task = self.task_entry.get().strip()

        if new_task == "":
            messagebox.showwarning("Empty Input", "Please enter a task.")
            return

        self.all_tasks.append(new_task)
        self.task_entry.delete(0, tk.END)
        self.refresh_listbox(self.all_tasks)

    # --- update existing task ---
    def update_task(self):
        selected = self.listbox.curselection()

        if not selected:
            messagebox.showerror("No Selection", "Select a task to update.")
            return

        updated_text = self.task_entry.get().strip()

        if updated_text == "":
            messagebox.showwarning("Empty Field", "Enter an updated value.")
            return

        # listbox is filtered sometimes, so we map selection
        visible_items = self.listbox.get(0, tk.END)
        old = visible_items[selected[0]]

        original_index = self.all_tasks.index(old)
        self.all_tasks[original_index] = updated_text

        self.task_entry.delete(0, tk.END)
        self.refresh_listbox(self.all_tasks)

    # --- delete selected task ---
    def delete_task(self):
        selected = self.listbox.curselection()

        if not selected:
            messagebox.showerror("No Selection", "Select a task to delete.")
            return

        visible_items = self.listbox.get(0, tk.END)
        item = visible_items[selected[0]]

        self.all_tasks.remove(item)
        self.refresh_listbox(self.all_tasks)


# ---- start the app ----
root = tk.Tk()
app = TaskManagerGUI(root)
root.mainloop()
```
