# Assignment 1

### Rafael Gallegos S929574

## Exercise 1

#### Write a C++ program that calculates n^n by declaring your own function. Note: n is an input from the user.

In order to solve the problem this code uses the cmath library which provides us with the pow function.
Although the problem states that we create our own function, it would have been much harder to do so because of the potensial use of decimal
numbers. The code in it self is quite simple, it starts by promptin the user to input the number, it then insert the number in the function.
Afterwards it prints out the result.

### The Code

```c++
#include <iostream>
#include <cmath>

using namespace std;

float thePower(float n);

int main()
{
	float m;
	float result;

	cout<<"Please input the number for n^n:"<<endl;
	cin>>m;

	result = thePower(m);
	cout<<"The result is: "<<result;

	return 0;
}

float thePower(float n)
{
	float results;

	results = pow(n,n);

	return results;
}
```
### The Results:
```
Please input the number for n^n:
5
The result is: 3125
```
## Exercise 2
#### Write a C++ program that sorts strings in alphabetical order (from a to z).

This program uses the algorithm and string library in order to solve the problem. By using string the program can read the whole set of characters
that are inputet by the user, then the sort function from the algorithm library sorts it in the right order. The result is then printed out.

### The code:
```c++
#include <iostream>
#include <algorithm>
#include <string>

using namespace std;

int main()
{
	string input;
	cout<<"Please input a string of characters: "<<endl;
	cin>>input;
	sort(input.begin(),input.end());

	cout<<"The line is now: "<<endl<<input<<endl;
	



	return 0;
}
```
### The Results
```
Please input a string of characters:
asdfghjklqwertyuiopzxcvbnm
The line is now:
abcdefghijklmnopqrstuvwxyz
```
## Exercise 3
#### Write a C++ program using an array that can hold twenty integers which should be input from the user. Display those input values on the screen, and then prompt the user for an element to be searched in this array. Finally, count the number of times the input element is found in the array.

This program uses a class called Array which has a static array with 20 elements. The class has three member values which sets the values, displays them and counts the number of times one of the elements are repeated.
The member functions do their tasks primarily by using for-loops in order to run through the array. In main the user is prompted to input the 20 values by using the setValues function, the values are then displayed using the displayvalues function.
The user selects the number he wishes to count, the input is used in the countSelected function, and the result is printed out.

### The code:

```c++
#include <iostream>

using namespace std;

class Array
{
private:
	int input[20];
public:
	Array();
	void setValues(int v);
	void displayValues();
	int countSelected(int b);
};

Array::Array(void)
{
	for (int i = 0; i < 20; ++i)
	{
		input[i] = 0;
	}
	cout<<"Object created and initialized to zero."<<endl;
}

void Array::setValues(int v)
{
	for (int i = 0; i < 20; ++i)
	{
		cin>>v;
		input[i] = v;
	}
}
void Array::displayValues()
{
	cout<<"The values you have entered are:"<<endl;
	for (int i = 0; i < 20; ++i)
	{
		cout<<input[i]<<" ";
	}
	cout<<endl;
}

int Array::countSelected(int b)
{
	int count = 0;
	for (int i = 0; i < 20; ++i)
	{
		if (b == input[i])
		{
			++count;
		}
	}
	return count;
}

int main()
{
	int input = 0;
	int select;

	Array myValues;
	cout<<"Please input 20 integer values:"<<endl;
	myValues.setValues(input);
	myValues.displayValues();
	cout<<"Please select a number you wish to search for in the array"<<endl;
	cin>>select;
	cout<<"The selected value was found: "<<myValues.countSelected(select);
	return 0;
}
```
### The Results
```
Object created and initialized to zero.
Please input 20 integer values:
1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0
The values you have entered are:
1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0
Please select a number you wish to search for in the array
5
The selected value was found: 2
```
## Exercise 4
#### Write a C++ program that creates a vector of 15 integer elements. Using an iterator, assign each element a value that is three times of its current value.

This code uses the vector library in order to solve the problem. The vector is first created and then filled with values from 1 to 15 using a for loop and the push_back function.
The vector is then displayed using a second for-loop. Each element in the vector is then multiplied by three using a third for-loop before it is displayed
using a fourth for-loop.

### The Code
```c++
#include <iostream>
#include <vector>

using namespace std;

int main()
{
	vector<int> myVector;

	for (int i = 1; i < 16; ++i)
	{
		myVector.push_back(i);
	}
	cout<<"The inital vector has the following elements:;"<<endl;
	for (int i = 0; i < 15; ++i)
	{
		cout<<myVector[i]<<" ";
	}
	for (int i = 0; i < 15; ++i)
	{
		myVector[i] = myVector[i]*3;
	}
	cout<<endl<<"The values multiplied by three are now:"<<endl;
	for (int i = 0; i < 15; ++i)
	{
		cout<<myVector[i]<<" ";
	}

	return 0;
}
```
### The Results:
```
The inital vector has the following elements:;
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
The values multiplied by three are now:
3 6 9 12 15 18 21 24 27 30 33 36 39 42 45
```
## Exercise 5
#### Write a C++ program that accepts five integer values from the user using pointers.

This program declares a five element array and a pointer which points to the first element. A for-loop is then used in order to get the values in the array,
using the pointer pluss the iterator the pointer fill each of the elements. Another for-loop is then used to display the values.

### The Code:
```c++
#include <iostream>

using namespace std;

int main()
{
	int mArray[5];
	int* p = mArray;
	cout<<"Please input 5 integer values."<<endl;
	for (int i = 0; i < 5; ++i)
	{
		cin>>*(p+i);
	}
	cout<<"The values you entered are:"<<endl;
	for (int i = 0; i < 5; ++i)
	{
		cout<<*(p+i)<<" ";
	}
	return 0;
}
```
### The Results:
```
Please input 5 integer values.
3 4 2 5 1
The values you entered are:
3 4 2 5 1
```
## Exercise 6
#### Write a C++ program that prints the elements of an array in a reverse order using pointers.

In order to solve the problem this program uses the algorithm function which uses the reverse funtion in order to re-order the elements in the array.
First a pointer is created which points to a dynamic array of size 15, then using pointers the array is filled with values. Then by using the reverse function the array is reversed and then displayed using a for-loop.

### The Code
```c++
#include <iostream>
#include <algorithm>

using namespace std;


int main()
{
	int* p = new int[15];
	for (int i = 0; i < 15; ++i)
	{
		*(p+i) = (i+1);
	}

	for (int i = 0; i < 15; ++i)
	{
		cout<<*(p+i)<<" ";
	}
	cout<<endl;

	reverse(p,p+15);

	for (int i = 0; i < 15; ++i)
	{
		cout<<*(p+i)<<" ";
	}


	return 0;
}
```
### The Results
```
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
15 14 13 12 11 10 9 8 7 6 5 4 3 2 1
```
## Exercise 7
#### Write a C++ program that finds the maximum of an integral data set. The program will first ask the user to input the number of data values in the set and finally should display a pointer that points to the maximum value of the data set.

The user is prompted to input the size of the dataset, then the dataset is filled using a for-loop which runs up to the size of the dataset.
The elements in the dataset are then runned though a second for-loop which finds the maximum value in the dataset and the address. The max value and its address is then diplayed in the end.

### The Code
```c++
#include <iostream>

using namespace  std;

int main()
{
	int n;
	int max = 0;
	int* maxP;
	cout<<"Enter the number of elements in your data set"<<endl;
	cin>>n;
	int* p = new int[n];
	for (int i = 0; i < n; ++i)
	{
		*(p+i) = (i+1);
	}
	for (int i = 0; i < n; ++i)
	{
		cout<<*(p+i)<<" ";
	}
	for (int i = 0; i < n; ++i)
	{
		if (*(p+i) >= max)
		{
			max = *(p+i);
			maxP = p;
		}
	}
	cout<<endl;

	cout<<"The maximal values is: "<<max<<endl;
	cout<<"The address of the value is: "<<maxP<<endl;

	return 0;
}
```
## The Results
```
Enter the number of elements in your data set
5
1 2 3 4 5
The maximal values is: 5
The address of the value is: 0xec19d0
```
## Exercise 8
#### Write a C++ class having private variables and two member functions which will return the area of a rectangle and a triangle.

The program uses a class with two private variables, two member functions and a constructor. The constructor is used to set the private values, 
the two member function triArea and rectArea are then used in cout to calculate the area of a triangle and a rectangle.

## The Code
```c++
#include <iostream>

using namespace std;

class Area 
{
private:
	int height, length;
public:
	Area(int x,int y);
	float triArea();
	float rectArea();
};

Area::Area(int x, int y)
{
	height = x;
	length = y;
}
float Area::triArea(void)
{
	float a;
	a = (1.0*height*length)/2;
	return a;
}

float Area::rectArea(void)
{
	float r;
	r = 1.0*height*length;
	return r;
}

int main()
{
	int l,h;
	cout<<"Enter the length:"<<endl;
	cin>>l;
	cout<<"Enter the height:"<<endl;
	cin>>h;

	Area myFigures(l,h);
	cout<<"The area of the triangle is:"<<myFigures.triArea()<<endl;
	cout<<"The area of the rectangle is:"<<myFigures.rectArea()<<endl;

	return 0;
}
```
### The Results
```
Enter the length:
5
Enter the height:
5
The area of the triangle is:12.5
The area of the rectangle is:25
```
## Exercise 9
#### Write a C++ program that takes an input of two integers in the main function and pass them to a default constructor of the class. Finally, display the result of an addition, subtraction, multiplication and division of the input integers.

The class uses two private variables, four member functions and one constructor. The constructor is used to set the variable values and then display the values.
When the object is created the getSum,getMin,getMult and getDiv are used and then the return values are displayed using cout.

### The Code
```c++
#include <iostream>

using namespace std;

class myClass
{
private:
	float a,b;

public:
	myClass(float x, float y);
	float getSum();
	float getMin();
	float getMult();
	float getDiv();
};

myClass::myClass(float x, float y)
{
	a = x;
	b = y;
	cout<<"Object created a = "<<a<<" b = "<<b<<endl;
}

float myClass::getSum()
{
	return a+b;
}
float myClass::getMin()
{
	return a-b;
}
float myClass::getMult()
{
	return a*b;
}
float myClass::getDiv()
{
	return a/b;
}

int main()
{
	myClass thisCalc(9,5);

	cout<<"9 + 5 = "<<thisCalc.getSum()<<endl;
	cout<<"9 - 5 = "<<thisCalc.getMin()<<endl;
	cout<<"9 x 5 = "<<thisCalc.getMult()<<endl;
	cout<<"9 / 5 = "<<thisCalc.getDiv()<<endl;

	return 0;
}
```
### The Results
```
Object created a = 9 b = 5
9 + 5 = 14
9 - 5 = 4
9 x 5 = 45
9 / 5 = 1.8
```
## Exercise 10
#### Write a C++ class named point that has three coordinates x, y, and z, where the coordinates are private. Create a function which is external to the class that computes the dot product between the coordinates.

The program uses a class point which has three private variables, one member function and one friend function. The friend function is used to access the
variables and calculate the dot product. In the setPoint function the *this* function is used to set the values of the private variables.
In main the objects are created, the function are used and the sum is displayed by using cout.

### The Code
```c++
#include <iostream>

using namespace std;

class point
{
private:
	int x,y,z;
public:
	friend int pointProduct(point point1, point point2);
	void setPoint(void);
};

void point::setPoint(void)
{
	cout<<"Enter the x value:"<<endl;
	cin>>this->x;
	cout<<"Enter the y value:"<<endl;
	cin>>this->y;
	cout<<"Enter the z value:"<<endl;
	cin>>this->z;
}

int pointProduct(point p1, point p2)
{
	int sum;
	sum = (p1.x*p2.x) + (p1.y*p2.y) + (p1.z*p2.z);
	return sum;
}

int main()
{
	int sum;
	point Point1;
	point Point2;
	cout<<"Enter the values for you first number."<<endl;
	Point1.setPoint();
	cout<<"Enter the values for you second number."<<endl;
	Point2.setPoint();

	sum = pointProduct(Point1, Point2);

	cout<<"The dot product of the two points are: "<<sum;

	return 0;
}
```
### The Results
```
Enter the values for you first number.
Enter the x value:
5
Enter the y value:
4
Enter the z value:
2
Enter the values for you second number.
Enter the x value:
3
Enter the y value:
7
Enter the z value:
1
The sum of the two products are: 45
```
