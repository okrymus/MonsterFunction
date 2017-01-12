// The program is an example how to use function which uses many function to proceed
// Monster Function
// Programmer: Panupong Leenawarat
// Last modified: 12/7/2015

#include <iostream>
#include <cstdlib>
#include "Functions Pototype.h"
using namespace std;

int main()                                                    //  main is DONE
{
	int select, intNumber;
	double number, startPoint, endPoint;
	char letter;

	system("COLOR 3F");
	
	while (true)
	{
		// print title
		printTitle();
		
		// print options that a user can choose
		printMenu();

		cout << "Please enter your choice: ";
		select = getIntInRange(1, 8);
		
		cout << endl;

		switch (select)
		{
		// Average a set of non - negative number
		case 1:                                                    //   DONE
			number = calcAverageOfInts();
			if (number < 0)
				cout << "There are no data to find the average";
			else
				cout << "\t" << "The average of the numbers is " << number;
		break;

		// check a input number in a custom range
		case 2:                                                    //   DONE
			cout << "What is the starting point? ";
			startPoint = getNum();
			cout << "What is the ending point? ";
			endPoint = getNum();

			cout << "\nEnter a number in the range[" << startPoint << ", " << endPoint << "]: ";
			number = getInRange(startPoint, endPoint);

			cout << "\tGood! " << number << " is a number in [" << startPoint << ", " << endPoint << "]" << endl << endl;
			break;
		
		// A letter
		case 3:                                                   //   DONE
			cout << "Enter a letter : ";
			letter = getLetter();

			cout << "\tGood! " << "\'" << letter << "\'" << " is a letter!" << endl << endl;
			break;
		
		// An integer
		case 4:                                                    //   DONE
			cout << "Please enter an integer: ";
			intNumber = getInteger();

			cout << "\tGood! " << intNumber << " is a integer" << endl << endl;
			break;
	    
		// A prime number 
		case 5:                                                    //   DONE
			cout << "Please enter an prime number: ";
			intNumber = getPrime();
			
			cout << "\t" << intNumber << " is prime number";
			break;
        
		// Classify a number
		case 6:                                                    //   DONE
			cout << "Please enter a number: ";
			intNumber = getIntBiggerThan(0);

			cout << "\t" << intNumber << " is ";
			switch (classifiesNumber(intNumber))
			{
			case -1: cout << "deficient";    break;
			case 0: cout << "perfect";      break;
			case 1: cout << "abundant";
			}
			break;
        
		// Print the ASCII table 
		case 7:                                                    //    DONE
			cout << "How many characters would you like to print per line ? [1, 4]: ";
			intNumber = getIntInRange(1, 4);
			cout << endl;

			printASCIITable(intNumber);  
			break;
		
		// Exit the program
		case 8:                                                    //   DONE
			cout << "Exiting the program" << endl << endl;
			system("pause");
			exit(0);  /// need to print a message
		}
		
		cout << endl << endl;
		system("pause");
		system("cls");
	}
}