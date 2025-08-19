## CodeForces Solved: 18

## Screenshot :

<img width="967" height="873" alt="image" src="https://github.com/user-attachments/assets/583f822a-abe4-4bb8-968f-61fbeb2a52cf" />

------------------------------
## Experiment No : 01

## Experiment Name : Write a C++ program to implement a class called Shape with virtual member 
## Submission Date : August 19, 2025

## Code :
```C++
#include <bits/stdc++.h>
using namespace std;

class Shape
{
public:
    virtual double area() const = 0;
    virtual double perimeter() const = 0;

    virtual ~Shape() {}
};

class Circle : public Shape
{
    double radius;

public:
    Circle(double r)
    {
        radius = r;
    }

    double area() const
    {
        return 3.1416 * radius * radius;
    }

    double perimeter() const
    {
        return 2 * 3.1416 * radius;
    }
};

class Rectangle : public Shape
{
    double length, width;

public:
    Rectangle(double l, double w)
    {
        length = l;
        width = w;
    }

    double area() const
    {
        return length * width;
    }

    double perimeter() const
    {
        return 2 * (length + width);
    }
};

class Triangle : public Shape
{
    double a, b, c;

public:
    Triangle(double side1, double side2, double side3)
    {
        a = side1;
        b = side2;
        c = side3;
    }

    double area() const
    {
        double s = (a + b + c) / 2.0;
        return sqrt(s * (s - a) * (s - b) * (s - c));
    }

    double perimeter() const 
    {
        return a + b + c;
    }
};

int main()
{

    Shape *shape;
    shape = new Circle(4);
    cout << "Area of Circle = " << shape->area() << endl;
    cout << "Perimeter of Circle = " << shape->perimeter() << endl;
    delete shape;
    shape = new Rectangle(3, 8);
    cout << endl << "Area of Rectangle = " << shape->area() << endl;
    cout << "Perimeter of Rectangle  = " << shape->perimeter() << endl;
    delete shape;
    shape = new Triangle(4, 8, 6);
    cout << endl << "Area of Triangle = " << shape->area() << endl;
    cout << "Perimeter of Triangle = " << shape->perimeter() << endl;
    delete shape;
}
```
------------

## Output : 
<img width="1231" height="448" alt="image" src="https://github.com/user-attachments/assets/0673402f-8fcc-40e1-bfc4-2f8a19c965c8" />


------------------------------

## Experiment No : 02 

## Experiment Name : Solve diamond shape problem (with virtual keyword). 

## Submission Date : August 19, 2025

## Code :
```C++

#include <bits/stdc++.h>
using namespace std;

class A {
public:
    int value;
};

class B : virtual public A {
public:
    void setB(int v) { value = v; }
};

class C : virtual public A {
public:
    void setC(int v) { value = v; }
};

class D : public B, public C {};

int main() {
    D obj;
    obj.setB(4); 
    obj.setC(5); 
    cout << obj.value;
}
```
---------------

## Output : 
<img width="1239" height="182" alt="image" src="https://github.com/user-attachments/assets/6ffdd97b-2989-4f0e-b863-dae58d4d80d3" />

---------------------------
## Experiment No : 02

## Experiment Name : Solve diamond shape problem (without virtual keyword). 

## Submission Date : August 19, 2025

## Code :
```C++
#include <bita/stdc++.h>
using namespace std;

class A {
public:
    int value;
};

class B : public A {
public:
    void setB(int v) { value = v; }
};

class C : public A {
public:
    void setC(int v) { value = v; }
};

class D : public B, public C {
public:
    void show() {

        cout << "Value from B: " << B::value << endl;
        cout << "Value from C: " << C::value << endl;
    }
};

int main() {
    D obj;
    obj.B::setB(10);
    obj.C::setC(20);
    obj.show();


}
```
------------------
## Output : 
<img width="1266" height="260" alt="image" src="https://github.com/user-attachments/assets/cc70e588-5442-489e-9139-ea2f457b414a" />

-------------------------
## Experiment No : 04

## Experiment Name : Create an abstract class Device. 

## Submission Date : August 19, 2025

## Code :
```C++
#include <bits/stdc++.h>
using namespace std;

class Device {
public:
    virtual void start() = 0; 
    void info() {
        cout << "Generic device information" << endl;
    }
    virtual ~Device() {}
};

class Printer : public Device {
public:
    void start() {
        cout << "Printer is started" << endl;
    }
};

class Scanner : public Device {
public:
    void start(){
        cout << "Scanner is started" << endl;
    }
};

int main() {
    Printer p;
    Scanner s;

    p.start();
    p.info();

    s.start();
    
    s.info();  
}
```
------------------
## Output : 
<img width="1261" height="301" alt="image" src="https://github.com/user-attachments/assets/ebba2daa-ba74-4770-b0ab-7baccc887c08" />
