import java.util.ArrayList;
import java.util.Scanner;

class Student {
    String name;
    ArrayList<Double> grades;

    public Student(String name) {
        this.name = name;
        this.grades = new ArrayList<>();
    }

    public void addGrade(double grade) {
        grades.add(grade);
    }

    public double getAverageGrade() {
        if (grades.isEmpty()) return 0.0;
        double total = 0.0;
        for (double grade : grades) {
            total += grade;
        }
        return total / grades.size();
    }

    public double getHighestGrade() {
        double highest = Double.MIN_VALUE;
        for (double grade : grades) {
            if (grade > highest) {
                highest = grade;
            }
        }
        return highest;
    }

    public double getLowestGrade() {
        double lowest = Double.MAX_VALUE;
        for (double grade : grades) {
            if (grade < lowest) {
                lowest = grade;
            }
        }
        return lowest;
    }

    @Override
    public String toString() {
        return name + " - Average: " + getAverageGrade() + ", Highest: " + getHighestGrade() + ", Lowest: " + getLowestGrade();
    }
}

class GradeTracker {
    private ArrayList<Student> students;

    public GradeTracker() {
        students = new ArrayList<>();
    }

    public void addStudent(String name) {
        students.add(new Student(name));
    }

    public Student getStudent(String name) {
        for (Student student : students) {
            if (student.name.equalsIgnoreCase(name)) {
                return student;
            }
        }
        return null; // If student not found
    }

    public void displayAllStudents() {
        for (Student student : students) {
            System.out.println(student);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        GradeTracker gradeTracker = new GradeTracker();

        while (true) {
            System.out.println("\nStudent Grade Tracker Menu:");
            System.out.println("1. Add Student");
            System.out.println("2. Add Grade");
            System.out.println("3. Display All Students");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            int option = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            if (option == 1) {
                System.out.print("Enter student name: ");
                String name = scanner.nextLine();
                gradeTracker.addStudent(name);
                System.out.println("Student added successfully.");
            } else if (option == 2) {
                System.out.print("Enter student name: ");
                String name = scanner.nextLine();
                Student student = gradeTracker.getStudent(name);
                if (student != null) {
                    System.out.print("Enter grade: ");
                    double grade = scanner.nextDouble();
                    student.addGrade(grade);
                    System.out.println("Grade added successfully.");
                } else {
                    System.out.println("Student not found.");
                }
            } else if (option == 3) {
                System.out.println("\nAll Students and their Grades:");
                gradeTracker.displayAllStudents();
            } else if (option == 4) {
                System.out.println("Exiting...");
                break;
            } else {
                System.out.println("Invalid option. Please try again.");
            }
        }

        scanner.close();
    }
}
