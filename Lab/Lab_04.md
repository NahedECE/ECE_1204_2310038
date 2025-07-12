## **Experiment No: 06**

## **Experiment Name: Demonstrate multilevel inheritance and polymorphism using virtual functions. Also, implement a function to find the student with the highest CGPA.**

## **Submission Date: 24 May, 2025**

----------

## **Discussion:**

In this program, we used **inheritance** and **polymorphism** to build a simple academic system for RUET. We created three classes: `RUET` (base), `ECE` (intermediate), and `STUDENT` (derived). Each class added more details — like department and CGPA.

We used **virtual functions** so that we could store `STUDENT` objects in an array of `RUET*` pointers and still call the correct `display()` method. This is an example of **runtime polymorphism**.

We also created a `findTopper()` function to find which student had the highest CGPA. The program takes data for 5 students and shows all their details, along with the topper’s info.

This helped us understand how inheritance, virtual functions, and dynamic binding work together in C++.

----------

## **Task 1: Polymorphism with Multilevel Inheritance**

Create a class hierarchy using `RUET`, `ECE`, and `STUDENT`, and store `STUDENT` objects in a `RUET*` array using virtual functions.

----------

## **Task 2: Find the Topper**

Create a function `findTopper()` to find the student with the highest CGPA using the same `RUET*` array.

----------

## **Code:**
```cpp
#include <iostream>
using namespace std;

class RUET {
protected:
    string name;
    int roll;

public:
    virtual void input() {
        cout << "Enter name: ";
        cin >> name;
        cout << "Enter roll: ";
        cin >> roll;
    }

    virtual void display() {
        cout << "Name: " << name << endl;
        cout << "Roll: " << roll << endl;
    }

    string getName() {
        return name;
    }

    int getRoll() {
        return roll;
    }

    virtual float getCGPA() {
        return 0.0;
    }
};

class ECE : public RUET {
protected:
    string dept_name;

public:
    void input() override {
        RUET::input();
        dept_name = "ECE";
    }

    void display() override {
        RUET::display();
        cout << "Department: " << dept_name << endl;
    }
};

class STUDENT : public ECE {
    float cgpa;

public:
    void input() override {
        ECE::input();
        cout << "Enter CGPA: ";
        cin >> cgpa;
    }

    void display() override {
        ECE::display();
        cout << "CGPA: " << cgpa << endl;
        if (cgpa > 3.75) {
            cout << "Honors Candidate" << endl;
        }
    }

    float getCGPA() override {
        return cgpa;
    }
};

void findTopper(RUET* students[], int n) {
    float maxCGPA = 0.0;
    int index = -1;
    for (int i = 0; i < n; ++i) {
        float current = students[i]->getCGPA();
        if (current > maxCGPA) {
            maxCGPA = current;
            index = i;
        }
    }

    if (index != -1) {
        cout << "\nTopper Information:\n";
        cout << "Name: " << students[index]->getName() << endl;
        cout << "Roll: " << students[index]->getRoll() << endl;
        cout << "CGPA: " << students[index]->getCGPA() << endl;
    }
}

int main() {
    const int size = 5;
    RUET* students[size];

    for (int i = 0; i < size; ++i) {
        students[i] = new STUDENT();
        cout << "\nEnter details for student " << i + 1 << ":\n";
        students[i]->input();
    }

    cout << "\nStudent Details:\n";
    for (int i = 0; i < size; ++i) {
        cout << "\nStudent " << i + 1 << ":\n";
        students[i]->display();
    }

    findTopper(students, size);

    for (int i = 0; i < size; ++i) {
        delete students[i];
    }

    return 0;
}
```

## **Output:**
<p align="center">

<img width="1132" height="819" alt="Image" src="https://github.com/user-attachments/assets/39cc0e23-f601-40cd-847e-8796a1f6ade8" />

</p>
