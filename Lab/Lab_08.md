## **Experiment No: 01**

## **Experiment Name: Create a simple calculator class with operator overloading.**

----------

## **Code:**
```C++
#include <iostream>
using namespace std;

class Calculator {
public:
    int a, b, c;

    Calculator(int x = 0, int y = 0) {
        a = x;
        b = y;
        c = 0;
    }

    Calculator operator+(Calculator obj) {
        Calculator temp;
        temp.c = (a + b) + (obj.a + obj.b);
        cout << "Addition: " << temp.c << endl;
        return temp;
    }

    Calculator operator-(Calculator obj) {
        Calculator temp;
        temp.c = (a - b) - (obj.a - obj.b);
        cout << "Subtraction: " << temp.c << endl;
        return temp;
    }

    Calculator operator*(Calculator obj) {
        Calculator temp;
        temp.c = (a * b) * (obj.a * obj.b);
        cout << "Multiplication: " << temp.c << endl;
        return temp;
    }

    Calculator operator/(Calculator obj) {
        Calculator temp;
        if (b != 0 && obj.b != 0) {
            temp.c = (a / b) / (obj.a / obj.b);
            cout << "Division: " << temp.c << endl;
        } else {
            cout << "Division by zero error!" << endl;
        }
        return temp;
    }

    Calculator operator++() {
        ++c;
        cout << "Prefix Increment: " << c << endl;
        return *this;
    }

    Calculator operator++(int) {
        Calculator temp = *this;
        c++;
        cout << "Postfix Increment: " << c << endl;
        return temp;
    }

    Calculator operator--() {
        --c;
        cout << "Prefix Decrement: " << c << endl;
        return *this;
    }

    Calculator operator--(int) {
        Calculator temp = *this;
        c--;
        cout << "Postfix Decrement: " << c << endl;
        return temp;
    }

    bool operator==(Calculator obj) {
        return c == obj.c;
    }
};

int main() {
    Calculator calc1(10, 5), calc2(20, 10);

    Calculator sumObj = calc1 + calc2;
    Calculator subObj = calc1 - calc2;
    Calculator mulObj = calc1 * calc2;
    Calculator divObj = calc1 / calc2;

    ++sumObj;
    sumObj++;
    --sumObj;
    sumObj--;

    Calculator newObj = calc1 + calc2;
    newObj++;
    newObj.c += 100;
    cout << "After adding 100: " << newObj.c << endl;

    Calculator compareObj(50, 50);
    compareObj.c = compareObj.a + compareObj.b;

    if (newObj == compareObj)
        cout << "newObj is equal to compareObj" << endl;
    else
        cout << "newObj is NOT equal to compareObj" << endl;

    return 0;
}
```

## **Output:**
<p align="center">
<img width="1469" height="386" alt="image" src="https://github.com/user-attachments/assets/d0d7b13a-87ab-4c8a-9c4c-f37e8c38fa67" />

## **Experiment No: 02**

## **Experiment Name: Create a class Rectangle demonstrating constructor overloading.**

----------

## **Code:**
```C++
#include <iostream>
using namespace std;

class Rectangle {
    double width, height;

public:
    Rectangle() {
        width = 1;
        height = 1;
    }

    Rectangle(double w, double h) {
        width = w;
        height = h;
    }

    double area() {
        return width * height;
    }
};

int main() {
    Rectangle r1;
    Rectangle r2(5.5, 3.2);

    cout << "Area of r1: " << r1.area() << endl;
    cout << "Area of r2: " << r2.area() << endl;

    return 0;
}
```

## **Output:**
<p align="center">
<img width="1473" height="462" alt="image" src="https://github.com/user-attachments/assets/64a9e4b9-3458-4e13-b691-79f6c4fabe6a" />
  
## **Experiment No: 03**

## **Experiment Name: Create a class Student with constructor overloading and dynamic memory allocation without using cstring.**

----------

## **Code:**
```C++
#include <iostream>
using namespace std;

class Student {
    char* name;
    int age;

    int strLength(const char* str) {
        int len = 0;
        while (str[len] != '\0') {
            len++;
        }
        return len;
    }

    void strCopy(char* dest, const char* src) {
        int i = 0;
        while (src[i] != '\0') {
            dest[i] = src[i];
            i++;
        }
        dest[i] = '\0';
    }

public:
    Student() {
        name = new char[50];
        const char* defaultName = "Unknown";
        strCopy(name, defaultName);
        age = 0;
    }

    Student(const char* n, int a) {
        int length = strLength(n);
        name = new char[length + 1];
        strCopy(name, n);
        age = a;
    }

    void display() {
        cout << "Name: " << name << ", Age: " << age << endl;
    }

    ~Student() {
        delete[] name;
    }
};

int main() {
    Student s1;
    Student s2("Alice", 20);

    cout << "Student 1: ";
    s1.display();

    cout << "Student 2: ";
    s2.display();

    return 0;
}
```

## **Output:**
<p align="center">
<img width="1479" height="274" alt="image" src="https://github.com/user-attachments/assets/0010887e-58e7-4f6f-9ddf-981f19faae5b" />
