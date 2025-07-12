## **Experiment No: 06**

## **Experiment Name: Demonstrate multilevel inheritance and polymorphism using virtual functions. Also, implement a function to find the student with the highest CGPA.**

## **Submission Date: 24 May, 2025**

----------

## **Discussion:**

This experiment demonstrates key object-oriented programming concepts such as **multilevel inheritance**, **virtual functions**, and **runtime polymorphism** in C++. 

The class hierarchy begins with a base class `RUET`, which stores basic student information (`name`, `roll`) and declares virtual methods for input and display. The `ECE` class inherits from `RUET` and adds department-specific behavior. Finally, the `STUDENT` class, which inherits from `ECE`, adds the `cgpa` field and logic to classify students as "Honors Candidates" based on CGPA.

An array of pointers to `RUET` is used to store `STUDENT` objects, showcasing polymorphism — where base class pointers call overridden methods in derived classes. This allows for dynamic method dispatch at runtime.

The program also implements a `findTopper()` function that identifies the student with the highest CGPA using the virtual `getCGPA()` method. This demonstrates how polymorphic behavior allows access to derived class data even through base class interfaces.

Memory is dynamically allocated and properly released using `delete` to avoid memory leaks.

In conclusion, this program effectively applies polymorphism and inheritance to build an academic system capable of handling student data flexibly and efficiently.

----------

## **Task 1: Polymorphism with Multilevel Inheritance**

Create the following class hierarchy:
- Base class `RUET`: name, roll, virtual input/display methods
- Derived class `ECE`: adds dept_name, overrides display
- Further derived class `STUDENT`: adds CGPA, overrides display

Use **virtual functions** and **an array of RUET pointers**, where each pointer stores a `STUDENT` object. Input data for at least **5 students** and display their details.

----------

## **Task 2: Find the Topper**

Create a function `findTopper()` that:
- Takes the array of `RUET*` (base class pointers)
- Returns the name and roll number of the student with the highest CGPA

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

<img src="https://github.com/user-attachments/assets/your_output_image4">

</p>

