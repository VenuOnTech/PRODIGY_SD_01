# Python Temperature Converter with GUI (Tkinter)

Features:  
  
Temperature Conversion: Convert temperatures between Celsius, Fahrenheit, and Kelvin.  
Multilingual Support: Use the gettext library for internationalization and localization.  
Save Result: Save the conversion result to a file.  
Theme Toggle: Switch between dark and light themes to change the appearance of the app.  

This is an enhanced Temperature Converter built using Python and the Tkinter GUI library. The application allows users to convert temperatures between Celsius, Fahrenheit, and Kelvin. Additionally, users can toggle themes, save results to a file, and interact with the program in multiple languages.

# Imported Modules & Their Functions

tkinter:  
  
tkinter is the standard Python interface to the Tk GUI toolkit. It is used for creating graphical user interfaces.  
tk.Label: Used to create text labels in the window.  
tk.Entry: A widget for text input, allowing users to enter temperatures.  
tk.Button: A button widget for user interaction (e.g., to trigger actions like converting temperature).  
tk.StringVar: A special variable that can be used to store and manage string data in Tkinter widgets (e.g., the result of the conversion).  

tkinter.ttk:  
  
The ttk module provides access to the Tk themed widgets, which provide a more modern appearance for GUI elements.  
ttk.Combobox: A drop-down menu that allows users to select units (Celsius, Fahrenheit, or Kelvin) for conversion.  

tkinter.messagebox:  
  
The messagebox module is used for creating pop-up dialog boxes that inform users of events, errors, or warnings.  
messagebox.showerror: Used to display an error message in a dialog box (e.g., when an invalid temperature is entered).  
messagebox.showinfo: Displays an informational message (e.g., to notify the user that the result was saved successfully).  
messagebox.showwarning: Displays a warning message (e.g., if the result is empty and the user tries to save it).  

tkinter.filedialog:  
  
The filedialog module allows users to interact with the file system. In this case, it's used for saving the conversion result to a file.  
asksaveasfilename: Opens a file dialog that allows the user to specify the location and name of the file to save the result to.

gettext:  
  
gettext is a module used to provide internationalization and localization (i18n and l10n) features. It allows the program to display text in different languages.  
gettext.bindtextdomain: Specifies the location of translation files (usually .mo files).  
gettext.textdomain: Sets the domain of translation (e.g., "temp_converter").
gettext.gettext: Retrieves the localized version of a string. _() is used as an alias for this function in the code, allowing easy translation of strings.
