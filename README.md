# CodeAlpha_task1
CGPA Calculator using cpp
/* Task 1: CGPA Calculator */
#include <iostream>
using namespace std;

struct Course {
    string name;
    int credits;
    float grade;
};

float calculateCGPA(Course courses[], int n) {
    float totalGradePoints = 0, totalCredits = 0;
    for (int i = 0; i < n; i++) {
        totalGradePoints += courses[i].grade * courses[i].credits;
        totalCredits += courses[i].credits;
    }
    return totalGradePoints / totalCredits;
}

int main() {
    int n;
    cout << "Enter number of courses: ";
    cin >> n;
    Course courses[n];
    for (int i = 0; i < n; i++) {
        cout << "Enter course name, credits and grade: ";
        cin >> courses[i].name >> courses[i].credits >> courses[i].grade;
    }
    cout << "Your CGPA is: " << calculateCGPA(courses, n) << endl;
    return 0;
}
