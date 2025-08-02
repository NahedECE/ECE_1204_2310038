## **Experiment No: 01**

## **Experiment Name: Write a C++ program using constructor overloading**


----------


## **Code:**
```C++
# include <iostream>
using namespace std;

class N{
    int n;
    public :
    N(){
        n =0;
    }
    N(int x){
        n=x;
    }
    void display(){
        cout<<"Number is = "<<n<<endl;
    }
};

int main(){
    N obj;
    obj.display();
    N obj1(10);
    obj1.display();
}

```

## **Output:**
<p align="center">
<img width="1462" height="199" alt="image" src="https://github.com/user-attachments/assets/92a25ae8-8f4a-46f0-ad4b-c06a504aac22" />


## **Experiment No: 02**

## **Experiment Name: Create  a  class  Student  that  demonstrates  constructor  overloading  with  dynamic memory allocation.**


----------


## **Code:**
```C++
# include <iostream>
using namespace std;

class Rectangle{
    int length,width;
    public :
    Rectangle(){
        length =1;
        width = 1;
    }
    Rectangle(int l,int w){
        length = l;
        width = w;
    }
    void area(){
        cout<<"Area is = "<<length*width<<endl;
    }
};

int main(){
    Rectangle o1,o2(12,12);
    o1.area();
    o2.area();
}

```

## **Output:**
<p align="center">
<img width="1460" height="241" alt="image" src="https://github.com/user-attachments/assets/f016ac8c-7376-4b87-af7f-c21fae97603b" />

## **Experiment No: 03**

## **Experiment Name: Create  a  class  Student  that  demonstrates  constructor  overloading  with  dynamic memory allocation. **


----------


## **Code:**
```C++
# include <iostream>
# include <string>
using namespace std;

class Student{
    int age;
    char* name;
    public :
    void copyString(char* dest, const char* src) {
        int i = 0;
        while (src[i] != '\0') {
            dest[i] = src[i];
            i++;
        }
        dest[i] = '\0';
    }
    Student(){
        name = new char[50];
        name = "Nahed";
        age = 0;
    }
    Student(char* n,int a){
        name = new char[50]; 
        copyString(name, n);
        age = a;  
    }
    void Display(){
        cout<<"Name is = "<<name<<"   "<<"Age is ="<<age<<endl;
    }
    ~Student(){
        delete [] name;
    }
};

int main(){
    Student s1,s2("Shakib",21);
    s1.Display();
    s2.Display();
}

```

## **Output:**
<p align="center">
<img width="1472" height="409" alt="image" src="https://github.com/user-attachments/assets/4bf810b1-fe8d-4777-8347-143746ca0b39" />

## **Experiment No: 04**

## **Experiment Name: Copy Constructor with Integer Pointer**


----------


## **Code:**
```C++
# include <iostream>
using namespace std;

class M{
    int *n = new int;
    public :
    M(int a){
        n = new int;
        *n = a;
          }
    M(const M& p){
        n = new int;
         *n = *p.n;
    }      
    void display(){
        cout << "Value = "<<*n<<" "<<"Address = "<<n<<endl;
    }
        };

int main(){
        M a(42);
        M b = a;
        a.display();
        b.display();
}

```

## **Output:**
<p align="center">
<img width="1461" height="159" alt="image" src="https://github.com/user-attachments/assets/383aa3a4-9774-4718-9441-1e657bec24c3" />






