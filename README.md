#include <iostream>
#include <string>
using namespace std;

class Book
{
    string name;
    int price;

public:
    // Default constructor
    Book()
    {
        name = "Unknown";
        price = 0;
    }

    // Parameterized constructor
    Book(string n, int p)
    {
        name = n;
        price = p;
    }

    // Overloading + operator
    Book operator+(Book b)
    {
        Book temp;
        temp.name = name + " & " + b.name;
        temp.price = price + b.price;
        return temp;
    }

    void display()
    {
        cout << "Book Name: " << name << endl;
        cout << "Total Price: " << price << endl;
    }
};

int main()
{
    Book b1("C++", 500);
    Book b2("Python", 300);

    cout << "First Book:" << endl;
    b1.display();

    cout << endl << "Second Book:" << endl;
    b2.display();

    Book b3 = b1 + b2;

    cout << endl << "After Operator Overloading:" << endl;
    b3.display();

    return 0;
}
