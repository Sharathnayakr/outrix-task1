import tkinter as tk
from tkinter import messagebox

# Function to evaluate expression
def calculate():
    try:
        result = eval(entry.get())
        entry.delete(0, tk.END)
        entry.insert(tk.END, str(result))
    except Exception as e:
        messagebox.showerror("Error", "Invalid Input")

# Function to update entry when button is clicked
def button_click(value):
    entry.insert(tk.END, value)

# Function to clear the entry
def clear():
    entry.delete(0, tk.END)

# Main Window
root = tk.Tk()
root.title("Basic Calculator")
root.geometry("300x400")

# Entry widget
entry = tk.Entry(root, width=20, font=('Arial', 18), bd=5, relief=tk.RIDGE, justify='right')
entry.grid(row=0, column=0, columnspan=4, pady=10)

# Buttons
buttons = [
    '7', '8', '9', '/',
    '4', '5', '6', '*',
    '1', '2', '3', '-',
    '0', 'C', '=', '+'
]

row_val = 1
col_val = 0

for button in buttons:
    if button == "C":
        tk.Button(root, text=button, width=5, height=2, font=('Arial', 14), 
                  command=clear).grid(row=row_val, column=col_val)
    elif button == "=":
        tk.Button(root, text=button, width=5, height=2, font=('Arial', 14), 
                  command=calculate).grid(row=row_val, column=col_val)
    else:
        tk.Button(root, text=button, width=5, height=2, font=('Arial', 14), 
                  command=lambda b=button: button_click(b)).grid(row=row_val, column=col_val)

    col_val += 1
    if col_val > 3:
        col_val = 0
        row_val += 1

# Run the application
root.mainloop()
