import tkinter as tk
from tkinter import ttk, messagebox
from tkinter.filedialog import asksaveasfilename
import gettext

# Localization setup
gettext.bindtextdomain("temp_converter", "locales")
gettext.textdomain("temp_converter")
_ = gettext.gettext

# Conversion functions
def convert_temperature():
    try:
        temp = float(entry_temperature.get())
        from_unit = combo_from_unit.get()
        to_unit = combo_to_unit.get()
        
        # Conversion logic
        if from_unit == "Celsius":
            if to_unit == "Fahrenheit":
                result_temp = (temp * 9/5) + 32
            elif to_unit == "Kelvin":
                result_temp = temp + 273.15
            else:
                result_temp = temp
        elif from_unit == "Fahrenheit":
            if to_unit == "Celsius":
                result_temp = (temp - 32) * 5/9
            elif to_unit == "Kelvin":
                result_temp = (temp - 32) * 5/9 + 273.15
            else:
                result_temp = temp
        elif from_unit == "Kelvin":
            if to_unit == "Celsius":
                result_temp = temp - 273.15
            elif to_unit == "Fahrenheit":
                result_temp = (temp - 273.15) * 9/5 + 32
            else:
                result_temp = temp
        
        # Display result
        result.set(f"{temp:.2f} {from_unit} = {result_temp:.2f} {to_unit}")

    except ValueError:
        messagebox.showerror(_("Error"), _("Please enter a valid numeric temperature."))

# Save result to a file
def save_result():
    if result.get():
        file_name = asksaveasfilename(defaultextension=".txt",
                                      filetypes=[("Text Files", "*.txt"), ("All Files", "*.*")])
        if file_name:
            with open(file_name, "w") as file:
                file.write(result.get())
            messagebox.showinfo(_("Success"), _("Result saved successfully!"))
    else:
        messagebox.showwarning(_("Warning"), _("No result to save!"))

# Theme toggle
def toggle_theme():
    current_theme = root.tk.call("ttk::style", "theme", "use")
    if current_theme == "clam":
        root.tk.call("ttk::style", "theme", "use", "default")
    else:
        root.tk.call("ttk::style", "theme", "use", "clam")

# Main application
root = tk.Tk()
root.title(_("Enhanced Temperature Converter"))

# Input fields
label_temperature = tk.Label(root, text=_("Enter Temperature:"))
label_temperature.grid(row=0, column=0, padx=10, pady=10)
entry_temperature = tk.Entry(root, width=20)
entry_temperature.grid(row=0, column=1, padx=10, pady=10)

# From unit dropdown
label_from_unit = tk.Label(root, text=_("From Unit:"))
label_from_unit.grid(row=1, column=0, padx=10, pady=10)
combo_from_unit = ttk.Combobox(root, values=["Celsius", "Fahrenheit", "Kelvin"], state="readonly")
combo_from_unit.grid(row=1, column=1, padx=10, pady=10)
combo_from_unit.set("Celsius")

# To unit dropdown
label_to_unit = tk.Label(root, text=_("To Unit:"))
label_to_unit.grid(row=2, column=0, padx=10, pady=10)
combo_to_unit = ttk.Combobox(root, values=["Celsius", "Fahrenheit", "Kelvin"], state="readonly")
combo_to_unit.grid(row=2, column=1, padx=10, pady=10)
combo_to_unit.set("Fahrenheit")

# Convert button
button_convert = tk.Button(root, text=_("Convert"), command=convert_temperature)
button_convert.grid(row=3, column=0, columnspan=2, pady=10)

# Save button
button_save = tk.Button(root, text=_("Save Result"), command=save_result)
button_save.grid(row=4, column=0, columnspan=2, pady=10)

# Toggle theme button
button_theme = tk.Button(root, text=_("Toggle Theme"), command=toggle_theme)
button_theme.grid(row=5, column=0, columnspan=2, pady=10)

# Result display
result = tk.StringVar()
label_result = tk.Label(root, textvariable=result, font=("Arial", 14))
label_result.grid(row=6, column=0, columnspan=2, pady=10)

# Run the application
root.mainloop()
