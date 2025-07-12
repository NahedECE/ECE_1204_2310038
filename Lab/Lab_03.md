## **Experiment No: 04**

## **Experiment Name: Write a program in C++ to demonstrate multilevel inheritance with access specifiers.**

## **Submission Date: 24 May, 2025**

----------

## **Code:**
```cpp
#include <iostream>
using namespace std;

class Base {
private:
    int privateBase;

protected:
    int protectedBase;

public:
    int publicBase;

    Base() {
        privateBase = 10;
        protectedBase = 20;
        publicBase = 30;
    }

    void showBase() {
        cout << "Base class:\n";
        cout << "  privateBase: " << privateBase << "\n";
        cout << "  protectedBase: " << protectedBase << "\n";
        cout << "  publicBase: " << publicBase << "\n";
    }
};

class Intermediate : public Base {
private:
    int privateIntermediate;

protected:
    int protectedIntermediate;

public:
    int publicIntermediate;

    Intermediate() {
        privateIntermediate = 40;
        protectedIntermediate = 50;
        publicIntermediate = 60;
    }

    void showIntermediate() {
        cout << "Intermediate class:\n";
        cout << "  protectedBase: " << protectedBase << "\n";
        cout << "  publicBase: " << publicBase << "\n";
        cout << "  privateIntermediate: " << privateIntermediate << "\n";
        cout << "  protectedIntermediate: " << protectedIntermediate << "\n";
        cout << "  publicIntermediate: " << publicIntermediate << "\n";
    }
};

class Derived : public Intermediate {
private:
    int privateDerived;

protected:
    int protectedDerived;

public:
    int publicDerived;

    Derived() {
        privateDerived = 70;
        protectedDerived = 80;
        publicDerived = 90;
    }

    void showDerived() {
        cout << "Derived class:\n";
        cout << "  protectedBase: " << protectedBase << "\n";
        cout << "  publicBase: " << publicBase << "\n";
        cout << "  protectedIntermediate: " << protectedIntermediate << "\n";
        cout << "  publicIntermediate: " << publicIntermediate << "\n";
        cout << "  privateDerived: " << privateDerived << "\n";
        cout << "  protectedDerived: " << protectedDerived << "\n";
        cout << "  publicDerived: " << publicDerived << "\n";
    }
};

int main() {
    Derived d;
    d.showBase();
    d.showIntermediate();
    d.showDerived();

    cout << "\nAccess from main():\n";
    cout << "  d.publicBase: " << d.publicBase << "\n";
    cout << "  d.publicIntermediate: " << d.publicIntermediate << "\n";
    cout << "  d.publicDerived: " << d.publicDerived << "\n";
    return 0;
}
```

## **Output:**
<p align="center">

<img src="https://github.com/user-attachments/assets/your_output_image1">

</p>

---

## **Experiment No: 05**

## **Experiment Name: Write a program in C++ to demonstrate constructors in multilevel inheritance.**

## **Submission Date: 24 May, 2025**

----------

## **Code:**
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    Base() {
        cout << "Constructor of Base class\n";
    }
};

class Intermediate : public Base {
public:
    Intermediate() {
        cout << "Constructor of Intermediate class\n";
    }
};

class Derived : public Intermediate {
public:
    Derived() {
        cout << "Constructor of Derived class\n";
    }
};

int main() {
    cout << "Creating object of Derived class:\n";
    Derived obj;
    return 0;
}
```

## **Output:**
<p align="center">

<img src="https://github.com/user-attachments/assets/your_output_image2">

</p>

