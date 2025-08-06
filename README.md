# Staxtech-Internship-project-
# Student management System 
// StudentManagementSystem.cpp - Enhanced Version
#include <iostream>
#include <vector>
using namespace std;

struct Student {
    int roll;
    string name;
    float marks;
};

vector<Student> students;

void addStudent() {
    Student s;
    cout << "Enter Roll No: ";
    cin >> s.roll;
    cout << "Enter Name: ";
    cin >> s.name;
    cout << "Enter Marks: ";
    cin >> s.marks;
    students.push_back(s);
    cout << "Student added successfully!\n";
}

void displayStudents() {
    cout << "\n--- Student List ---\n";
    for (const auto& s : students) {
        cout << "Roll: " << s.roll << ", Name: " << s.name << ", Marks: " << s.marks << endl;
    }
}

void searchStudent() {
    int roll;
    cout << "Enter roll number to search: ";
    cin >> roll;
    for (const auto& s : students) {
        if (s.roll == roll) {
            cout << "Found: Roll: " << s.roll << ", Name: " << s.name << ", Marks: " << s.marks << endl;
            return;
        }
    }
    cout << "Student not found!\n";
}

void deleteStudent() {
    int roll;
    cout << "Enter roll number to delete: ";
    cin >> roll;
    for (auto it = students.begin(); it != students.end(); ++it) {
        if (it->roll == roll) {
            students.erase(it);
            cout << "Student deleted successfully!\n";
            return;
        }
    }
    cout << "Student not found!\n";
}

void updateStudent() {
    int roll;
    cout << "Enter roll number to update: ";
    cin >> roll;
    for (auto& s : students) {
        if (s.roll == roll) {
            cout << "Enter new name: ";
            cin >> s.name;
            cout << "Enter new marks: ";
            cin >> s.marks;
            cout << "Student updated successfully!\n";
            return;
        }
    }
    cout << "Student not found!\n";
}

int main() {
    int choice;
    do {
        cout << "\n1. Add Student\n2. Display Students\n3. Search Student\n4. Delete Student\n5. Update Student\n6. Exit\nEnter choice: ";
        cin >> choice;
        switch (choice) {
            case 1: addStudent(); break;
            case 2: displayStudents(); break;
            case 3: searchStudent(); break;
            case 4: deleteStudent(); break;
            case 5: updateStudent(); break;
            case 6: cout << "Exiting...\n"; break;
            default: cout << "Invalid choice!\n";
        }
    } while (choice != 6);

    return 0;
}
