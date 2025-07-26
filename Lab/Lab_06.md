## CodeForces Solved: 02

## Screenshot
<img width="1132" height="440" alt="image" src="https://github.com/user-attachments/assets/f94f4ff8-4d2e-441a-8ce5-bbe2e2bb3c19" />



## **Experiment No: 01**

## **Experiment Name: Create a class Student with attributes name, roll, and marks. Initialize an array of 5 students and write a program to input and display the data for all students.**


----------


## **Code:**
```C++
#include <iostream>
using namespace std;
class Student
{
    string name;
    int roll;
    int marks;

public:
    void input()
    {
        cout << "Enter Name =";
        cin >> name;
        cout << "Enter Roll =";
        cin >> roll;
        cout << "Enter Marks =";
        cin >> marks;
    }
    void show()
    {
        cout << "Name = " << name << endl;
        cout << "Roll = " << roll << endl;
        cout << "Name = " << marks << endl;
    }
};

int main()
{
    Student s[3];
    for (int i = 0; i < 2; i++)
    {
        cout << "Data for Student " << i + 1 << endl;
        s[i].input();
    }
    for (int i = 0; i < 2; i++)
    {
        cout << "Display for Student " << i + 1 << endl;
        s[i].show();
    }
    return 0;
}


```

## **Output:**
<p align="center">
<img width="1454" height="467" alt="image" src="https://github.com/user-attachments/assets/5a31c6d8-e420-4f88-8b11-f1f9d80f8dfa" />


## **Experiment No: 02**

## **Experiment Name: Create a class Book with a function display(). Create a pointer to a Book object and call display() using that pointer. Allocate memory dynamically.**


----------


## **Code:**
```C++
#include <iostream>
using namespace std;
class Book
{
    string name = "Teach Yourself C++";

public:
    void Display()
    {
        cout << "Name = " << name << endl;
    }
};
int main()
{
    Book *b1 = new Book;
    b1->Display();
    delete b1;
}

```

## **Output:**
<p align="center">
<img width="1456" height="198" alt="image" src="https://github.com/user-attachments/assets/3fe09ec8-3f00-4f1b-80e8-6b765631a651" />


## **Experiment No: 03**

## **Experiment Name:Create a class Rectangle with private members length and breadth. Use the this pointer to differentiate between local and member variables in the constructor. **


----------


## **Code:**
```C++
#include <iostream>
using namespace std;
class Rectangle
{
    int Width;
    int breadth;

public:
    void input(int r, int m)
    {

        this->Width = r;
        this->breadth = m;
    }
    void show()
    {
        cout << "Width = " << Width << endl;
        cout << "Breadth = " << breadth << endl;
    }
};

int main()
{
    Rectangle R;
    R.input(10, 15);
    R.show();
}

```

## **Output:**
<p align="center">
<img width="1466" height="222" alt="image" src="https://github.com/user-attachments/assets/4724e261-936f-46d5-a0bc-dc4490347167" />

## **Experiment No: 04**

## **Experiment Name: Create a program to dynamically allocate memory for an array of 10 integers, input values, calculate their sum, and deallocate memory properly using delete. **


----------


## **Code:**
```C++
#include <iostream>
using namespace std;
int main()
{
    int *arr = new int[10];
    for (int i = 0; i < 10; i++)
    {
        cout << "Enter value fot index " << i + 1 << " = ";
        cin >> arr[i];
    }
    int sum = 0;
    for (int i = 0; i < 10; i++)
    {
        sum += arr[i];
    }

    cout << "Sum = " << sum << endl;
    delete[] arr;
}

```

## **Output:**
<p align="center">
<img width="1458" height="332" alt="image" src="https://github.com/user-attachments/assets/55b92563-f352-408a-96ee-4e65251ef1d0" />


## **Experiment No: 05**

## **Experiment Name: Create  a  class  Employee  that  has  a  constructor  and  destructor.  Dynamically  allocate  an object of this class and verify constructor and destructor execution using new and delete.**


----------


## **Code:**
```C++
#include <iostream>
using namespace std;
class Employee
{
public:
    Employee()
    {
        cout << "Constructor Called" << endl;
    }
    ~Employee()
    {
        cout << "Destructor Called" << endl;
    }
};
int main()
{
    Employee *N = new Employee();
    delete N;
}

```

## **Output:**
<p align="center">
<img width="1462" height="232" alt="image" src="https://github.com/user-attachments/assets/b666e319-2b9e-44a3-931f-4e1a2e673280" />

## **Experiment No: 06**

## **Experiment Name:Write a function that takes an integer by reference and increments its value by 1. Show that the original value is changed outside the function. **


----------


## **Code:**
```C++
#include <iostream>
using namespace std;
void increment(int &a)
{
    a++;
}
int main()
{
    int x;
    cout << "Enter a number = ";
    cin >> x;
    increment(x);
    cout << "Incremented value = " << x << endl;
}

```

## **Output:**
<p align="center">
<img width="1465" height="241" alt="image" src="https://github.com/user-attachments/assets/a66f5632-4730-4426-9a8e-393c5d19789b" />

## **Experiment No: 07**

## **Experiment Name:Create a class Account with balance. Write a function that accepts an object of Account by reference and adds money to the balance. **


----------


## **Code:**
```C++
#include <iostream>
using namespace std;
class Account
{
public:
    double balance;
    Account(double b)
    {
        balance = b;
    }
};
void add(Account &a, double amount)
{
    a.balance += amount;
}
int main()
{
    Account x(1500);
    add(x, 500);
    cout << "New balance = " << x.balance << endl;
}

```

## **Output:**
<p align="center">
<img width="1456" height="191" alt="image" src="https://github.com/user-attachments/assets/1f55b5ca-cc7c-4f4f-b232-8fd01f9ca52b" />

## **Experiment No: 09**

## **Experiment Name:Create  a  function  swapValues(int  &a,  int  &b)  that  swaps  two  integers  using  references. Then create a function sortDescending(int &x, int &y, int &z) that uses swapValues() to sort the three integers in descending order using only reference passing.**


----------


## **Code:**
```C++
#include <iostream>
using namespace std;
void swap(int &a, int &b)
{
    int temp;
    temp = a;
    a = b;
    b = temp;
}
void sortDescending(int &x, int &y, int &z)
{
    if (x > y)
    {
        swap(x, y);
    }
    if (x > z)
    {
        swap(x, z);
    }
    if (y > z)
    {
        swap(y, z);
    }
}
int main()
{
    int b = 4, c = 5, d = 8, e = 7, f = 9;
    cout << "Before Swaping : " << endl;
    cout << "b = " << b << " c = " << c << endl;
    cout << "After Swaping : " << endl;
    swap(b, c);
    cout << "b = " << b << " c = " << c << endl;
    cout << "Before Sorting : " << endl;
    cout << "d = " << d << " e = " << e << " f = " << f << endl;
    cout << "After Sorting : " << endl;
    sortDescending(d, e, f);
    cout << "d = " << d << " e = " << e << " f = " << f << endl;
}


```

## **Output:**
<p align="center">
<img width="1466" height="316" alt="image" src="https://github.com/user-attachments/assets/e914c2b5-600d-420d-a052-52bcc6cc4c0b" />




















