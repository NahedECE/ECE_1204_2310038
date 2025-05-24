

## **Experiment No: 01**

## **Experiment Name: Write a program in C++ to find area and perimeter of a rectangle.**

## **Submission Date: 24 May, 2025**

----------


## **Code:**
```C
# include <iostream>
using namespace std;

class Rectangle{
    private :
    int length,width;

    public:
    void data(int l, int w){
        length = l;
        width = w;
    }
    int area(){
    int area = length * width;
    return area;
}
int peri(){
    int perimeter = 2*(length + width);
    return perimeter;
}

};

int main (){
    int l,w;
    cout<<"Enter length = ";
    cin>>l;
    cout<<"Enter width = ";
    cin>>w;
    Rectangle ob;
    ob.data(l,w);
    cout<<"Area is = "<<ob.area()<<endl;
    cout<<"Perimeter is = "<<ob.peri()<<endl;
}

  




```

## **Output:**
<p align="center">

<img src="https://github.com/user-attachments/assets/cf75e66f-e7ef-4eee-a70f-5e6b6069e598">

</p>

## **Experiment No: 02**

## **Experiment Name: Write a program in C++ for trying to access public, private, protected methods & attributes.**

## **Submission Date: 24 May, 2025**

----------


## **Code:**
```C

#include <iostream>
using namespace std;
class student
{
private:
    int x;
    int p1();

public:
    int y;
    int p2();

protected:
    int z;
    int p3();
};
int student ::p1()
{
    return 1;
}
int student ::p2()
{
    return 2;
}
int student ::p3()
{
    return 3;
}
int main()
{
    student n;
    // private
    // cin>>n.x;
    // cout<<n.x;
    // cout<<n.p1();
    // public
    cin >> n.y;
    cout << n.y <<endl;
    cout << n.p2();
    // protected
    // cin>>n.z;
    // cout<<n.z;
    // cout<<n.p3();
}



```

## **Output:**
<p align="center">

<img src="https://github.com/user-attachments/assets/bd1d415f-36e3-41d6-9fdc-257e3c7cb62c">

</p>

## **Experiment No: 03**

## **Experiment Name: Write a C++ program to set and get data using construct.**

## **Submission Date: 24 May, 2025**

----------


## **Code:**
```C
# include <iostream>
using namespace std;
class car{
private :
string company,model,year;
public :
// void set(string c1,string m1,string y1){
//        company = c1;
//        model = m1;
//        year = y1;
// }
car(string c1,string m1,string y1){
       company = c1;
       model = m1;
       year = y1;
}
void get(){
    cout<<"Company = "<<company<<endl;
    cout<<"Model = "<<model<<endl;
    cout<<"Year = "<<year<<endl;
}

};

int main(){
    string c,m,y;
    cout<<"Company = ";
    cin>>c;
    cout<<"Model = ";
    cin>>m;
    cout<<"Year = ";
    cin>>y;
    car car1(c,m,y);
    car1.get();  
    return 0;
}

     

```

## **Output:**
<p align="center">

<img  src="https://github.com/user-attachments/assets/11a52bb4-8903-4a9e-91e5-c0508abce604">

</p>



