# Task Manager (Python Tkinter Desktop App)
 
A lightweight desktop Task Manager built with Python and Tkinter, featuring a clean dark-themed interface, live search filtering, and full task management — add, update, and delete — all with zero external dependencies.
 
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-informational)
![License](https://img.shields.io/badge/License-MIT-green)
 
---

## 📋 Overview

Task Manager GUI is a simple, no-frills desktop application for tracking day-to-day tasks. It's built entirely with Python's standard library (`tkinter`), so there's nothing extra to install — just run the script and start managing tasks.

The app demonstrates core GUI development concepts such as event-driven programming, widget layout management, and syncing a visual list with an underlying data model — making it a great reference project for anyone learning Tkinter.

---

## ✨ Features

- ➕ **Add Tasks** — Quickly add new tasks to your list
- ✏️ **Update Tasks** — Edit the text of any existing task
- 🗑️ **Delete Tasks** — Remove tasks you no longer need
- 🔍 **Live Search** — Filter tasks in real time as you type, without modifying the underlying data
- 🎨 **Dark Mode UI** — A consistent dark color palette with color-coded action buttons (green = add, blue = update, red = delete)
- 📜 **Scrollable List** — Easily browse through longer task lists via an integrated scrollbar

---

## 🖥️ Tech Stack

| Component | Technology |
|---|---|
| Language | Python 3 |
| GUI Framework | Tkinter (standard library) |
| Dependencies | None |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.x installed on your machine
- Tkinter (included by default with most Python installations)

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/task-manager-gui.git
   cd task-manager-gui
   ```

2. Run the application:
   ```bash
   python b.py
   ```

No `pip install` required — the app runs out of the box.

---

## 🧭 How to Use

1. **Add a task** — Type a task into the "Enter Task" field and click **Add Task**.
2. **Search tasks** — Start typing in the "Search Task" field to filter the list live.
3. **Update a task** — Select a task from the list, type the new text into the "Enter Task" field, and click **Update Task**.
4. **Delete a task** — Select a task from the list and click **Delete Task**.

---

## ⚙️ How It Works

- Tasks are stored in memory in a Python list for the duration of the session (no file or database persistence).
- The search bar filters the *displayed* list only — the underlying task data is never altered by a search.
- Update and delete operations map the currently selected row back to the correct item in the full task list, ensuring accuracy even when a search filter is active.

---
