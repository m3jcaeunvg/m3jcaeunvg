
Fri 8:31 PM
You sent
import time
from tkinter import *
from tkinter import messagebox

def validate_model(model):
    valid_models = ["sedan", "hatchback", "SUV", "pickup", "sports car"]
    if model.lower() in valid_models:
        return True
    else:
        return False

def print_maintenance_schedule(model):
    maintenance_schedule = ""
    if model.lower() == "sedan":
        maintenance_schedule = "\nMaintenance Schedule for Sedan:\n" \
                              "Oil change: Every 5,000 km\n" \
                              "Air filter: Every 20,000 km\n" \
                              "Brake pads: Every 50,000 km"
    elif model.lower() == "hatchback":
        maintenance_schedule = "\nMaintenance Schedule for Hatchback:\n" \
                              "Oil change: Every 5,000 km\n" \
                              "Air filter: Every 20,000 km\n" \
                              "Brake pads: Every 50,000 km"
    elif model.lower() == "suv":
        maintenance_schedule = "\nMaintenance Schedule for SUV:\n" \
                              "Oil change: Every 5,000 km\n" \
                              "Air filter: Every 20,000 km\n" \
                              "Brake pads: Every 50,000 km"
    elif model.lower() == "pickup":
        maintenance_schedule = "\nMaintenance Schedule for Pickup:\n" \
                              "Oil change: Every 5,000 km\n" \
                              "Air filter: Every 20,000 km\n" \
                              "Brake pads: Every 50,000 km"
    elif model.lower() == "sports car":
        maintenance_schedule = "\nMaintenance Schedule for Sports Car:\n" \
                              "Oil change: Every 3,000 km\n" \
                              "Air filter: Every 10,000 km\n" \
                              "Brake pads: Every 30,000 km"
    return maintenance_schedule

def show_warning(message):
    messagebox.showwarning("Warning", message)

def submit_registration():
    name = name_entry.get().strip()
    model = model_entry.get().strip()
    background_info = background_entry.get().strip()

    if name == "":
        messagebox.showerror("Error", "Please enter your name.")
        return

    if not validate_model(model):
        messagebox.showerror("Error", "Invalid model. Please enter a valid model name.")
        return

    messagebox.showinfo("Registration Complete", f"Thank you for the information, {name}!\nYour {model} "
                                                  f"has been registered in the telemetry system.")

    if background_info != "":
        messagebox.showinfo("Additional Information", f"Additional information: {background_info}")

def start_monitoring():
    MAX_SPEED = 120
    MAX_RPM = 7000

    def monitor_vehicle():
        try:
            vehicle_speed = float(speed_entry.get())
            engine_rpm = int(rpm_entry.get())
            fuel_level = float(fuel_entry.get())

            if vehicle_speed < 0 or engine_rpm < 0 or fuel_level < 0:
                show_warning("Input values must be positive.")
                return

            if vehicle_speed > MAX_SPEED:
                show_warning("Vehicle speed is above the limit!")

            if engine_rpm > MAX_RPM:
                show_warning("Vehicle RPM is above the limit!")

            if fuel_level < 5:
                show_warning("Vehicle fuel level is low!")

            maintenance_schedule = print_maintenance_schedule(model_entry.get())
            # Rest of the code for monitoring the vehicle goes here
            # ...

        except ValueError:
            show_warning("Invalid input. Please enter numeric values for the vehicle speed, engine RPM, and fuel level.")
          import time
from tkinter import *
from tkinter import messagebox

def validate_model(model):
    valid_models = ["sedan", "hatchback", "SUV", "pickup", "sports car"]
    if model.lower() in valid_models:
        return True
    else:
        return False

def print_maintenance_schedule(model):
    maintenance_schedule = ""
    if model.lower() == "sedan":
        maintenance_schedule = "\nMaintenance Schedule for Sedan:\n" \
                              "Oil change: Every 5,000 km\n" \
                              "Air filter: Every 20,000 km\n" \
                              "Brake pads: Every 50,000 km"
    elif model.lower() == "hatchback":
        maintenance_schedule = "\nMaintenance Schedule for Hatchback:\n" \
                              "Oil change: Every 5,000 km\n" \
                              "Air filter: Every 20,000 km\n" \
                              "Brake pads: Every 50,000 km"
    elif model.lower() == "suv":
        maintenance_schedule = "\nMaintenance Schedule for SUV:\n" \
                              "Oil change: Every 5,000 km\n" \
                              "Air filter: Every 20,000 km\n" \
                              "Brake pads: Every 50,000 km"
    elif model.lower() == "pickup":
        maintenance_schedule = "\nMaintenance Schedule for Pickup:\n" \
                              "Oil change: Every 5,000 km\n" \
                              "Air filter: Every 20,000 km\n" \
                              "Brake pads: Every 50,000 km"
    elif model.lower() == "sports car":
        maintenance_schedule = "\nMaintenance Schedule for Sports Car:\n" \
                              "Oil change: Every 3,000 km\n" \
                              "Air filter: Every 10,000 km\n" \
                              "Brake pads: Every 30,000 km"
    return maintenance_schedule

def show_warning(message):
    messagebox.showwarning("Warning", message)

def submit_registration():
    name = name_entry.get().strip()
    model = model_entry.get().strip()
    background_info = background_entry.get().strip()

    if name == "":
        messagebox.showerror("Error", "Please enter your name.")
        return

    if not validate_model(model):
        messagebox.showerror("Error", "Invalid model. Please enter a valid model name.")
        return

    messagebox.showinfo("Registration Complete", f"Thank you for the information, {name}!\nYour {model} "
                                                  f"has been registered in the telemetry system.")

    if background_info != "":
        messagebox.showinfo("Additional Information", f"Additional information: {background_info}")

def start_monitoring():
    MAX_SPEED = 120
    MAX_RPM = 7000

    def monitor_vehicle():
        try:
            vehicle_speed = float(speed_entry.get())
            engine_rpm = int(rpm_entry.get())
            fuel_level = float(fuel_entry.get())

            if vehicle_speed < 0 or engine_rpm < 0 or fuel_level < 0:
                show_warning("Input values must be positive.")
                return

            if vehicle_speed > MAX_SPEED:
                show_warning("Vehicle speed is above the limit!")

            if engine_rpm > MAX_RPM:
                show_warning("Vehicle RPM is above the limit!")

            if fuel_level < 5:
                show_warning("Vehicle fuel level is low!")

            maintenance_schedule = print_maintenance_schedule(model_entry.get())
            if fuel_level == 0:
                show_warning("Fuel level is zero. Please refuel the vehicle.")

 root.destroy()

root = Tk()
root.title("Telemetry System")

# Registration Section
registration_frame = Frame(root)
registration_frame.pack(pady=10)

name_label = Label(registration_frame, text="Name:")
name_label.grid(row=0, column=0, padx=10, pady=5)
name_entry = Entry(registration_frame)
name_entry.grid(row=0, column=1, padx=10, pady=5)

model_label = Label(registration_frame, text="Model:")
model_label.grid(row=1, column=0, padx=10, pady=5)
model_entry = Entry(registration_frame)
model_entry.grid(row=1, column=1, padx=10, pady=5)

background_label = Label(registration_frame, text="Background Information:")
background_label.grid(row=2, column=0, padx=10, pady=5)
background_entry = Entry(registration_frame)
background_entry.grid(row=2, column=1, padx=10, pady=5)

register_button = Button(root, text="Register", command=submit_registration)
register_button.pack(pady=5)

# Monitoring Section
monitoring_frame = Frame(root)
monitoring_frame.pack(pady=10)

speed_label = Label(monitoring_frame, text="Vehicle Speed (km/h):")
speed_label.grid(row=0, column=0, padx=10, pady=5)
speed_entry = Entry(monitoring_frame)
speed_entry.grid(row=0, column=1, padx=10, pady=5)

rpm_label = Label(monitoring_frame, text="Engine RPM:")
rpm_label.grid(row=1, column=0, padx=10, pady=5)
rpm_entry = Entry(monitoring_frame)
rpm_entry.grid(row=1, column=1, padx=10, pady=5)

fuel_label = Label(monitoring_frame, text="Fuel Level (liters):")
fuel_label.grid(row=2, column=0, padx=10, pady=5)
fuel_entry = Entry(monitoring_frame)
fuel_entry.grid(row=2, column=1, padx=10, pady=5)

start_button = Button(root, text="Start Monitoring", command=start_monitoring)
start_button.pack(pady=5)

root.mainloop()

print("\nMonitoring stopped by the user.")

root = Tk()
root.title("Telemetry System")

# Registration Section
registration_frame = Frame(root)
registration_frame.pack(pady=10)

name_label = Label(registration_frame, text="Name:")
name_label.grid(row=0, column=0, padx=10, pady=5)
name_entry = Entry(registration_frame)
name_entry.grid(row=0, column=1, padx=10, pady=5)

model_label = Label(registration_frame, text="Model:")
model_label.grid(row=1, column=0, padx=10, pady=5)
model_entry = Entry(registration_frame)
model_entry.grid(row=1, column=1, padx=10, pady=5)

background_label = Label(registration_frame, text="Background Information:")
background_label.grid(row=2, column=0, padx=10, pady=5)
background_entry = Entry(registration_frame)
background_entry.grid(row=2, column=1, padx=10, pady=5)

register_button = Button(root, text="Register", command=submit_registration)
register_button.pack(pady=5)

# Monitoring Section
monitoring_frame = Frame(root)
monitoring_frame.pack(pady=10)

speed_label = Label(monitoring_frame, text="Vehicle Speed (km/h):")
speed_label.grid(row=0, column=0, padx=10, pady=5)
speed_entry = Entry(monitoring_frame)
speed_entry.grid(row=0, column=1, padx=10, pady=5)

rpm_label = Label(monitoring_frame, text="Engine RPM:")
rpm_label.grid(row=1, column=0, padx=10, pady=5)
rpm_entry = Entry(monitoring_frame)
rpm_entry.grid(row=1, column=1, padx=10, pady=5)

fuel_label = Label(monitoring_frame, text="Fuel Level (liters):")
fuel_label.grid(row=2, column=0, padx=10, pady=5)
fuel_entry = Entry(monitoring_frame)
fuel_entry.grid(row=2, column=1, padx=10, pady=5)

start_button = Button(root, text="Start Monitoring", command=start_monitoring)
start_button.pack(pady=5)

root.mainloop()

print("\nMonitoring stopped by the user.")
