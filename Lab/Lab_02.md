## **Experiment No : 01**

## **Experiment Name : Program to generate employee bonus**

## **Submission Date : June 13, 2025**

## Code :
```C++
#include <iostream>
using namespace std;

class Employee {
private:
    string name;
    int employeeID;
    double baseSalary;
public:
    Employee(string n, int id, double salary) : name(n), employeeID(id), baseSalary(salary) {}
    friend class HRDepartment;
};

class PermanentEmployee : public Employee {
private:
    int yearsOfService;
public:
    PermanentEmployee(string n, int id, double salary, int years) : Employee(n, id, salary), yearsOfService(years){}
    friend class HRDepartment;
};

class ContractEmployee : public Employee {
private:
    int contractDuration;
public:
    ContractEmployee(string n, int id, double salary, int duration) : Employee(n, id, salary), contractDuration(duration) {}
    friend class HRDepartment;
};

class HRDepartment {
public:
    void calculateBonus(PermanentEmployee& emp) {
        double bonus = 0.1 * emp.baseSalary + 1000 * emp.yearsOfService;
        cout << "Bonus for Permanent Employee " << emp.name << ": " << bonus << endl;
    }

    void calculateBonus(ContractEmployee& emp) {
        double bonus = 0.05 * emp.baseSalary;
        cout << "Bonus for Contract Employee " << emp.name << ": " << bonus << endl;
    }
};

int main() {
    PermanentEmployee em1("Mahi", 1001, 50000, 3);
    ContractEmployee em2("Nahed", 1002, 40000, 5);

    HRDepartment hr;
    hr.calculateBonus(em1);
    hr.calculateBonus(em2);

    return 0;
}


```

## **Output :** 
![Image](https://github.com/user-attachments/assets/d56dd575-b55c-4065-b741-d67691d44530)






## **Experiment No : 02**

## **Experiment Name : Program to generate costs**

## **Submission Date : June 13, 2025**

## Code :
```C++
#include <iostream>
using namespace std;

class TeamMember {
private:
    string name;
    int memberID;
    double hourlyRate;
public:
    TeamMember(string n, int id, double rate) : name(n), memberID(id), hourlyRate(rate) {}
    friend class ProjectManager;
};

class Developer : public TeamMember {
private:
    int linesOfCodeWritten;
public:
    Developer(string n, int id, double rate, int lines) : TeamMember(n, id, rate), linesOfCodeWritten(lines) {}
    friend class ProjectManager;
};

class Tester : public TeamMember {
private:
    int bugsFound;
public:
    Tester(string n, int id, double rate, int bugs) : TeamMember(n, id, rate), bugsFound(bugs) {}
    friend class ProjectManager;
};

class ProjectManager {
public:
    void calculateCost(Developer& d) {
        double cost = d.hourlyRate * 160 + 0.1 * d.linesOfCodeWritten;
        cout << "Cost for Developer " << d.name << ": " << cost << endl;
    }
    void calculateCost(Tester& t) {
        double cost = t.hourlyRate * 160 + 50 * t.bugsFound;
        cout << "Cost for Tester " << t.name << ": " << cost << endl;
    }
};

int main() {
    Developer dev("Rafid", 101, 200, 4000);     
    Tester test("Shakib", 102, 150, 40);  

    ProjectManager pm;

    pm.calculateCost(dev);
    pm.calculateCost(test);
}


```

## **Output :** 
![Image](https://github.com/user-attachments/assets/07bfae82-3bd0-4ace-a9ac-24a86e36d621)



## **Experiment No : 03**

## **Experiment Name : Program to calculate Prime Numbers Within a Range**

## **Submission Date : June 13, 2025**

## Code :
```C++
#include <iostream>
using namespace std;

class PrimeFinder {
private:
    int start, end;
public:
    PrimeFinder(int s, int e) {
        start = s;
        end = e;
    }

    void findPrimes() {
        int total = 0;
        cout << "The prime numbers between " << start << " and " << end << " are:\n";
        for (int i = start; i <= end; i++) {
            int count = 0;
            for (int j = 2; j <= i / 2; j++)
            {
                if (i == 1) {continue;}
                else if (i % j == 0)
                {
                    count++;
                }
            }
            if (count == 0 && i != 1)
            {
                cout << i << " ";
                total++;
            }

        }
        cout << "\nThe total number of prime numbers between " << start << " to " << end << " is: " << total << endl;
    }
};

int main() {

    int start, end;
    cout << "Input number for starting range: ";
    cin >> start;
    cout << "Input number for ending range: ";
    cin >> end;

    PrimeFinder pf(start, end);
    pf.findPrimes();

}


```

## **Output :** 
![Image](https://github.com/user-attachments/assets/060d9498-4ce7-42a2-9bfe-a378ab17f0eb)



## **Experiment No : 04**

## **Experiment Name : Program to find the factorial of a number.**

## **Submission Date : June 13, 2025**

## Code :
```C++

#include <iostream>
using namespace std;

class Number {
private:
    int num;
public:
    void input() {
        cout << "Input a number to find the factorial: ";
        cin >> num;
    }
    friend class FactorialCalculator;
};

class FactorialCalculator {
public:
    void factorial(Number &n) {
        int fact = 1;
        for (int i = 1; i <= n.num; i++) {
            fact *= i;
        }
        cout << "The factorial of the given number is: " << fact << endl;
    }
};

int main() {
    Number n;
    FactorialCalculator calc;

    n.input();           
    calc.factorial(n); 

}

```

## **Output :** 
![Image](https://github.com/user-attachments/assets/996dbbff-d847-402d-8648-fe7568edf8ee)





## **Experiment No : 05**

## **Experiment Name : Program to find Volume of a Cube**

## **Submission Date : June 13, 2025**

## Code :
```C++
#include <iostream>
using namespace std;

class Cube {
private:
    int side;
public:
    Cube(int s) {
        side = s;
    }
    int volume() {
        return side * side * side;
    }
};

int main() {
    int s;
    cout << "Calculate the volume of a cube :" << endl;
    cout << "---------------------------------------" << endl;
    cout << "Input the side of a cube : ";
    cin >> s;

    Cube c(s);

    cout << "The volume of a cube is : " << c.volume() << endl;

    return 0;
}


```

## **Output :** 
![Image](https://github.com/user-attachments/assets/882044f6-7cb3-4608-837b-b59367438993)



