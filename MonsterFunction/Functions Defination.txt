#include "Functions Pototype.h"
#include <iostream>
#include <iomanip>
#include <string>
using namespace std;

void printTitle()             //   DONE
{
	cout
		<< endl
		<< "\t          Sample Monster Function Lab(while, for, switch)          " << endl
		<< "\t               includes review of switch as a menu                 " << endl
		<< "\t            function reusanility and \"slave\" functions           " << endl
		<< "\t                        By Lee. Panupong                           " << endl << endl;
}

void printMenu()            //   DONE
{
	cout
		<< "        1] Average a set of non - negative numbers(sentinel)                 " << endl
		<< "        2] Enter a number in a given range                                   " << endl
		<< "        3] Enter a letter                                                    " << endl
		<< "        4] Enter an integer                                                  " << endl
		<< "        5] Enter a prime number                                              " << endl
		<< "        (needs \"slave\" function isPrime, calls getIntBiggerThan)           " << endl
		<< "        6] Classify a number as deficient, perfect, or abundant(think strcmp)" << endl
		<< "        7] Print the ASCII table                                             " << endl
		<< "        8] End the program                                                   " << endl << endl;
}

double calcAverageOfInts()        
{
	int count = 1, intNumber = 0;
	double sum = 0;
		
	cout << "Please enter the 1" << getOrdinalFor(1) << " number: ";
	intNumber = getInteger();
	
	if (count = 1 && intNumber < 0)
	{
		return -1;
	}

	while (intNumber >= 0)
	{
		cout << "Please enter the " << ++count << getOrdinalFor(count) << " number: ";
		sum += intNumber;
		intNumber = getInteger();
	}
	return sum / (count);   
}

string getOrdinalFor(int value)   
{
	int hundredRemainder = value % 100;
	int tenRemainder = value % 10;
	
	if (hundredRemainder - tenRemainder == 10)
		return "th" ; 
	else
		switch (tenRemainder)
		{
		case 1:	return "st" ;  
		case 2: return "nd" ;     
		case 3:	return "rd" ;   
		default: return "th" ;
		}
}

double getInRange(double startPoint, double endPoint)             //   DONE
{
	double number = getNum();

	while (number < startPoint || number > endPoint)
	{
		cout << "\tYour number must be ";
		if (number < startPoint)
			cout << "greater than or equal " << startPoint;
		else 
			cout << "less than or equal " << endPoint;

		cout << ". Try again: ";
		number = getNum();
	}
	return number;
}

int getIntInRange(double startPoint, double endPoint)             //   DONE   
{
	int number = getInteger();
	
	while (number < startPoint || number > endPoint)
	{
		cout << "\t" << "Your number must be ";
		if (number < startPoint)
			cout << "greater than or equal " << startPoint;
		else
			cout << "less than or equal " << endPoint;

		cout << ". Try again: ";
		number = getInteger();
	}
	return (int)number;
}

char getLetter()             //   DONE
{
	char letter;
	
	cin >> letter;	cin.ignore(80, '\n');

	while ((!(letter >= 'a' && letter <= 'z') && !(letter >= 'A' && letter <= 'Z')))
	{
		cout << "\t" << letter << " is NOT a letter. Try again: ";
		cin >> letter;	cin.ignore(80, '\n');
	}
	return letter;
}

int getInteger()             //   DONE
{
	double number = getNum();

	while (number != (int)number)
	{
		cout << "\t" << number << " is NOT an integer. Try again: ";
		number = getNum();
	}
	return int(number);
}

int getPrime()             //   DONE
{
	int number = getIntBiggerThan(2);
	
	while (!(isPrime(number)))  
	{
		cout << "\t" << number << " is not prime number. Try Again: ";
		number = getIntBiggerThan(2);
	}
	return number;
}

bool isPrime(int number)
{
	for (int count = 2; count < number; count++)  
	{
		if (number % count == 0)
			return false;
	}
	return true;
}

int classifiesNumber(int number)   
{
	int sumOfFactors = 0;
	
	for (int count = 1; count <= number; count++)
		if(number % count == 0)  sumOfFactors += count;

	if (sumOfFactors < number)
		return -1;
	else if (sumOfFactors == number)
		return 0;
	else
		return 1;
}

void printASCIITable(int line)             //   DONE
{
	char letter;
	
	for (int count = 0; count <= 255; count++)
	{
		letter = count;
		cout << setw(5) << count << "" << setw(5);
		switch (letter)
		{
		case '\0': cout << setw(5) << "null";   break;
		case '\a': cout << setw(5) << "\\a";    break;
		case '\b': cout << setw(5) << "\\b";    break;
		case '\t': cout << setw(5) << "\\t";    break;
		case '\n': cout << setw(5) << "\\n";    break;
		case '\v': cout << setw(5) << "\\v";    break;
		case '\r': cout << setw(5) << "\\r";    break;
		default:  cout << setw(5) << letter;
		}
	cout << setw(4) << "||" << ((count+1) % line == 0 ? "\n" : "");
	}
}

int getIntBiggerThan(int number)             //   DONE
{
	int value = getInteger();

	while (value <= number)
	{
		cout << "\t" << "Please enter a integer bigger than " << number << ": ";
		value = getInteger();
	}
	return value;
}

double getNum()             //   DONE
{
	double number;
	
	while (!(cin >> number))
	{
		cout << "\tNo letters please. Try again: ";
		cin.clear();
		cin.ignore(80, '\n');
	}
	cin.ignore(80, '\n');
	return number;
} 