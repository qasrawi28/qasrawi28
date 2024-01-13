from tkinter import *
from tkinter import messagebox

# Create The Main App Window
age_app = Tk()

# Change App Text عنوان التطبيق
age_app.title("saif project")

# Set Dimensionsعشان حجم النافذة
age_app.geometry("400x200")

# Write Age Label
the_text = Label(age_app, text="Write Your Age", height=2, font=("Arial", 20))
the_text.pack()  # Place The Text Into The Main Window يضيف النص على النافذة

# Age Variables عشان نقدر نعدل عليه
age = StringVar()

# Set Default Value For Ageعملنا ديفولت فاليو
age.set("00")

# Create The Input For Age widthيعني 2 كركتر جنب بعض
# fontنوعه arial وحجمه 30
# textvariable هو الفاريابيل الموجود جوا الinput
age_input = Entry(age_app, width=2, font=("Arial", 30), textvariable=age)
age_input.pack()  # Place The Input Into The Main Window

def calc():

  # Get Age In Years
  # نخزنه جوا فاريابيل
  # getتجيبلي القيمة اللي الشخص كتبها
  the_age_value = age.get()

  # Get Time Units
  months = int(the_age_value) * 12
  weeks = months * 4
  days = int(the_age_value) * 365
  # لظهورهم عند الضغط على الفنكشن
  line_one = f"Your Age In Months Is: {months}"
  line_two = f"Your Age In Weeks Is: {weeks}"
  line_three = f"Your Age In Days Is: {days}"

  # List Contain All Lines
  all_lines = [line_one, line_two, line_three]

  # Message Box To Show All Lines 
  messagebox.showinfo("Your Age In All Time Units", "\n".join(all_lines))

# Create The Calculate Button
# bg لون
# fgاللون نفسه
# command لما تكبس الكبسة بشتغل الفنكشن
# borderwidth شكل الزر
btn = Button(age_app, text="Calculate Age", width=20,
height=2, bg="#e91e63", fg="white", borderwidth=0, command=calc)
btn.pack()  # Place Button in The Main Window

# Run App Infinitely
age_app.mainloop()
