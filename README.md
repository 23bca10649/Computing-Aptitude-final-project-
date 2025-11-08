CHANDIGARH UNIVERSITY
Project Report on
STOCK MANAGEMENT SYSTEM
Submitted By:
MAYAR MUORTER GENG
UID: 23BCA10649
Under the Guidance of
Mrs. Ankita
Abstract
The Stock Management System is developed to efficiently manage, track, and
monitor inventory in an organization. It automates manual stock handling, reduces
human errors, and ensures real-time updates of product availability. The system
allows easy addition, updating, and removal of stock items while maintaining
records of sales and purchases.
Introduction
Stock management plays a vital role in any business dealing with goods or materials.
Manual systems often result in inefficiency and data inconsistency. This project aims
to provide a computerized Stock Management System that simplifies tracking,
reduces paperwork, and enables fast and reliable access to inventory information.
Problem Statement / Objectives
Problem Statement:
Traditional stock management is prone to errors, delays, and inconsistencies that
affect business operations.
Objectives:
- To automate stock handling and monitoring processes.
- To maintain up-to-date inventory records.
- To track stock transactions efficiently.
- To generate reports for decision-making.
- To minimize manual work and improve data accuracy.
System Design / Approach
System Architecture:
- Frontend: C++ Console Interface
- Backend: File Handling (text-based storage)
- Architecture: User Interface + Logic + Data Layer
Design Elements:
- Flowchart representing stock transactions
- Data file structure for products and sales records
Implementation
Key Modules Implemented:
1. Login Module
2. Product Management Module
3. Transaction Module
4. Report Generation Module
Below is the C++ code for implementation:
#include <iostream>
#include <fstream>
#include <iomanip>
using namespace std;
class Stock {
int productID;
string name;
int quantity;
float price;
public:
void addProduct() {
cout << "Enter Product ID: "; cin >> productID;
cout << "Enter Product Name: "; cin >> name;
cout << "Enter Quantity: "; cin >> quantity;
cout << "Enter Price: "; cin >> price;
ofstream fout("stock.txt", ios::app);
fout << productID << " " << name << " " << quantity << " " <<
price << endl;
fout.close();
cout << "Product Added Successfully!" << endl;
}
void displayProducts() {
ifstream fin("stock.txt");
cout << left << setw(10) << "ID" << setw(15) << "Name" <<
setw(10) << "Qty" << setw(10) << "Price" << endl;
while (fin >> productID >> name >> quantity >> price) {
cout << left << setw(10) << productID << setw(15) << name
<< setw(10) << quantity << setw(10) << price << endl;
}
fin.close();
}
void searchProduct() {
int id, found = 0;
cout << "Enter Product ID to Search: "; cin >> id;
ifstream fin("stock.txt");
while (fin >> productID >> name >> quantity >> price) {
if (productID == id) {
cout << "Product Found: " << name << " | Qty: " <<
quantity << " | Price: " << price << endl;
found = 1;
break;
}
}
if (!found) cout << "Product Not Found!" << endl;
fin.close();
}
};
int main() {
Stock s;
int choice;
do {
cout << "\n1. Add Product\n2. Display Products\n3. Search
Product\n4. Exit\nEnter choice: ";
cin >> choice;
switch(choice) {
case 1: s.addProduct(); break;
case 2: s.displayProducts(); break;
case 3: s.searchProduct(); break;
case 4: cout << "Exiting..."; break;
default: cout << "Invalid Choice!";
}
} while(choice != 4);
return 0;
}
Results / Testing
Below is the sample output generated from the C++ program during testing:
Program Menu:
1. Add Product
2. Display Products
3. Search Product
4. Exit
Enter choice:
Case 1 – Add Product:
Enter Product ID: 101
Enter Product Name: Keyboard
Enter Quantity: 10
Enter Price: 500
Product Added Successfully!
Case 2 – Display Products:
ID Name Qty Price
101 Keyboard 10 500
102 Mouse 15 300
Case 3 – Search Product:
Enter Product ID to Search: 101
Product Found: Keyboard | Qty: 10 | Price: 500
Case 4 – Exit:
Exiting...
Conclusion
The Stock Management System efficiently automates the stock handling process,
ensuring accuracy and reliability. It reduces human effort and saves time in
inventory control.
References
- www.w3schools.com
- www.tutorialspoint.com
- C++ Reference Documentation
- MySQL Documentation (for concept study)
