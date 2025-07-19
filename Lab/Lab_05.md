## **Experiment No: 01**

## **Experiment Name: Create a class Box that represents a 3D box with length, width, and height.**


----------


## **Code:**
```C
#include <iostream>
using namespace std;

class box
{
    int length, height, width;

public:
    box(int l, int w, int h)
    {
        length = l;
        width = w;
        height = h;
    }
    inline int volume()
    {
        return length * width * height;
    }

    inline void compareVolume(box other)
    {
        if (this->volume() > other.volume())
            cout << "Box 1 has a larger volume." << endl;
        else if (this->volume() < other.volume())
            cout << "Box 2 has a larger volume." << endl;
        else
            cout << "Both boxes have the same volume." << endl;
    }
};

int main()
{
    box b1(3, 4, 5), b2(5, 6, 8);
    cout << "Volume of box 1" << b1.volume() << endl;
    cout << "Volume of box 2" << b2.volume() << endl;
    b1.compareVolume(b2);
    return 0;
}
  




```

## **Output:**
<p align="center">

<img width="1466" height="201" alt="Image" src="https://github.com/user-attachments/assets/daab6ff3-1d98-4807-ae24-0e897958382c" />

## **Experiment No: 02**

## **Experiment Name: Create a class stack with a character array **



----------


## **Code:**
```C
#include <iostream>
using namespace std;

class Stack
{
    char arr[10];
    int tos;

public:
    Stack()
    {
        tos = 0;
    }

    void push(char ch)
    {
        if (tos < 10)
        {
            arr[tos++] = ch;
        }
        else
        {
            cout << "Stack overflow" << endl;
        }
    }

    char pop()
    {
        if (tos > 0)
        {
            return arr[--tos];
        }
        else
        {
            cout << "Stack underflow" << endl;
            return '\0';
        }
    }

    bool isEmpty()
    {
        return tos == 0;
    }
};

int main()
{
    Stack s1, s2;
    s1.push('a');
    s1.push('b');
    s1.push('c');

    s2 = s1;

    cout << "Stack 1: ";
    while (!s1.isEmpty())
    {
        cout << s1.pop() << ' ';
        ;
    }

    cout << "Stack 2: ";
    while (!s2.isEmpty())
    {
        cout << s2.pop() << ' ';
    }

    return 0;
}

    

  




```

## **Output:**
<p align="center">

<img width="1460" height="130" alt="Image" src="https://github.com/user-attachments/assets/c3c47157-2c70-4191-b3dc-cd73824f6c2f" />


## **Experiment No: 03**

## **Experiment Name: Create a class Person with the following attributes.**



----------


## **Code:**
```C

   #include <iostream>
using namespace std;

class person
{
    string name;
    int age;
    string city;

public:
    person(string n, int a, string c)
    {
        name = n;
        age = a;
        city = c;
    }
    void display()
    {
        cout << "Name: " << name << ", Age: " << age << ", City: " << city << endl;
    }
    void update_person_info(person &p, int nage, string ncity)
    {
        p.age = nage;
        p.city = ncity;
    }
};

int main()
{
    person p1("Nahed", 20, "Barisal");
    cout << "Before updation: " << endl;
    p1.display();
    p1.update_person_info(p1, 21, "Rajshahi");
    cout << "After Updation: " << endl;
    p1.display();
}
  




```

## **Output:**
<p align="center">

<img width="1415" height="174" alt="Image" src="https://github.com/user-attachments/assets/da956765-2220-42c7-9941-ab3be894fec1" />

## **Experiment No: 04**

## **Experiment Name: 1. Dynamically Create an Object of a Class Using New 2. Dynamically Create an Array of Objects Using New 3. Dynamically Allocate Memory for a Structure and Input Its Members.**



----------


## **Code:**
```C
#include <iostream>
using namespace std;
// Dynamically Create an Object of a Class Using New
class Animal
{
public:
    void Show()
    {
        cout << " Food for animal" << endl;
    }
};
//  Dynamically Create an Array of Objects Using New

int main()
{
    cout << "Dynamically created object of a class using new" << endl;
    Animal *Cat = new Animal;
    Cat->Show();
    delete Cat;
    cout << "Dynamically created Array of object using new" << endl;
    int n = 3;
    Animal *arr = new Animal[n];

    for (int i = 0; i < n; i++)
    {
        arr[i].Show();
    }

    delete[] arr;
}


```

## **Output:**
<p align="center">

<img width="1006" height="263" alt="Image" src="https://github.com/user-attachments/assets/049ffdae-957a-4e94-b02a-4d4c27f8d020" />
