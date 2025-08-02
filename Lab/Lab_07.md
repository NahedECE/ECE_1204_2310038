## **Experiment No: 01**

## **Experiment Name: Create a class Student with attributes name, roll, and marks. Initialize an array of 5 students 
and write a program to input and display the data for all students. **


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
    Student s[5];
    for (int i = 0; i < 5; i++)
    {
        cout << "Data for Student " << i + 1 << endl;
        s[i].input();
    }
    for (int i = 0; i < 5; i++)
    {
        cout << "Display for Student " << i + 1 << endl;
        s[i].show();
    }
    return 0;
}



```

## **Output:**
<p align="center">

