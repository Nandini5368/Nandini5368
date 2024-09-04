def input_grades():
    grades = {}
    print("Enter grades for each subject or assignment.")
    print("Type 'done' when you have finished entering grades.")
    
    while True:
        subject = input("Enter the subject/assignment name: ").strip()
        if subject.lower() == 'done':
            break
        try:
            grade = float(input(f"Enter the grade for {subject} (0-100): "))
            if 0 <= grade <= 100:
                grades[subject] = grade
            else:
                print("Grade must be between 0 and 100. Please try again.")
        except ValueError:
            print("Invalid input. Please enter a numeric value for the grade.")
    
    return grades

def calculate_average(grades):
    if not grades:
        return 0
    return sum(grades.values()) / len(grades)

def display_grades(grades, average):
    print("\nGrades Summary")
    print("--------------")
    for subject, grade in grades.items():
        print(f"{subject}: {grade:.2f}")
    
    print(f"\nAverage Grade: {average:.2f}")
    
    if average >= 90:
        performance = "Excellent"
    elif average >= 80:
        performance = "Good"
    elif average >= 70:
        performance = "Average"
    elif average >= 60:
        performance = "Pass"
    else:
        performance = "Fail"
    
    print(f"Overall Performance: {performance}")

def main():
    print("Student Grade Tracker")
    print("----------------------")
    
    grades = input_grades()
    average = calculate_average(grades)
    display_grades(grades, average)

if __name__ == "__main__":
    main() date
