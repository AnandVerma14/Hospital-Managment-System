patients = []
def add_patient():
    name = input("Enter Name:")
    id = input("Enter Patient ID:")
    age = input("Enter Age: ")
    contact = input("Enter Contact: ")
    diagnosis = input("Enter Diagnosis:")
    patient = {'Name': name,'ID': id,'Age': age,'Contact': contact,'Diagnosis': diagnosis}
    patients.append(patient)
    print("Patient added successfully.")
def view_patients():
    if patients:
        print("All Patients:")
        for patient in patients:
            print(patient)
    else:
        print("No patients found.")
def search_patient():
    id = input("Enter Patient ID to search: ")
    for patient in patients:
        if patient['ID'] == id:
            print("Patient found:", patient)
            return
    print("Patient not found.")
def update_patient():
    id = input("Enter Patient ID to update: ")
    for patient in patients:
        if patient['ID'] == id:
            print("Enter new details (press Enter to keep current value):")
            name = input(f"Name [{patient['Name']}]: ") or patient['Name']
            age = input(f"Age [{patient['Age']}]: ") or patient['Age']
            contact = input(f"Contact [{patient['Contact']}]: ") or patient['Contact']
            diagnosis = input(f"Diagnosis [{patient['Diagnosis']}]: ") or patient['Diagnosis']
            patient.update({'Name': name, 'Age': age, 'Contact': contact, 'Diagnosis': diagnosis})
            print("Patient updated successfully.")
            return
    print("Patient not found.")
def delete_patient():
    pid = input("Enter Patient ID to delete: ")
    for i, patient in enumerate(patients):
        if patient['ID'] == pid:
            del patients[i]
            print("Patient deleted successfully.")
            return
    print("Patient not found.")
def main_menu():
    while True:
        print("Hospital Patient Management System")
        print("1. Add Patient")
        print("2. View All Patients")
        print("3. Search Patient")
        print("4. Update Patient")
        print("5. Delete Patient")
        print("6. Exit")
        choice = input("Select an option (1-6):")
        if choice == '1':
            add_patient()
        elif choice == '2':
            view_patients()
        elif choice == '3':
            search_patient()
        elif choice == '4':
            update_patient()
        elif choice == '5':
            delete_patient()
        elif choice == '6':
            print("Exiting the program. Goodbyee!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main_menu()
