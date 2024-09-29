# Initialize an empty dictionary to store student grades
student_grades = {}

def add_student():
    name = input("Enter student's name: ")
    grades = input("Enter grades (space-separated): ").split()
    grades = [float(grade) for grade in grades]
    student_grades[name] = grades
    print(f"Student {name} added successfully.")

def update_grades():
    name = input("Enter student's name: ")
    if name in student_grades:
        grades = input("Enter new grades (space-separated): ").split()
        grades = [float(grade) for grade in grades]
        student_grades[name] = student_grades[name] + grades
        print(f"Grades for {name} updated successfully.")
    else:
        print(f"Student {name} not found.")

def view_grades():
    name = input("Enter student's name: ")
    if name in student_grades:
        print(f"Grades for {name}: {student_grades[name]}")
    else:
        print(f"Student {name} not found.")

def calculate_average_grade():
    name = input("Enter student's name: ")
    if name in student_grades:
        average_grade = sum(student_grades[name]) / len(student_grades[name])
        print(f"Average grade for {name}: {average_grade:.2f}")
    else:
        print(f"Student {name} not found.")

def exit_program():
    print("Exiting program. Goodbye!")
    global student_grades
    student_grades = {}
    return

def main():
    while True:
        print("\nStudent Grade Management System")
        print("1. Add Student")
        print("2. Update Grades")
        print("3. View Student Grades")
        print("4. Calculate Average Grade")
        print("5. Exit Program")
        choice = input("Enter your choice: ")
        
        if choice == "1":
            add_student()
        elif choice == "2":
            update_grades()
        elif choice == "3":
            view_grades()
        elif choice == "4":
            calculate_average_grade()
        elif choice == "5":
            exit_program()
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
