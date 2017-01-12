#include <string>
using namespace std;

// Functions Pototype

// Pre condition:  NONE
// Post condition: Print a centered title for the program
void printTitle();     //  DONE

// Pre condition:  NONE
// Post condition: Print a menu for the program
void printMenu();     //  DONE

// Pre condition:  value >= 1
//                 Which is used find an ordinal number of the value
// Post condition: return an ordinal letter of the value such as "th", "rd" and "st"
string getOrdinalFor(int value);     //  DONE

// Pre condition:  endPoint > startPoint
// Post condition: Return a double number which is in the range
//                 it does NOT crashes for non-numeric input
//                 removes everything else from the cin
double getInRange(double startPoint, double endPoint);     //  DONE

// Pre condition:  endPoint > startPoint
// Post condition: Return a integer number which is in the range
//                 it does NOT crashes for non-numeric input
//                 removes everything else from the cin
int getIntInRange(double startPoint, double endPoint);     //  DONE

// Pre condition:  NONE
// Post condition: Return a number 
//                 which is the average of Integers
//                 it asks for only possitive numbers to find the avarage
//                 it does NOT crashes for non-numeric input
//                 removes everything else from the cin
double calcAverageOfInts();

// Pre condition:  NONE
// Post condition: Return a letter character
//                 it takes only a letter from A to Z and a-z
//                 removes everything else from the cin
char getLetter();     //  DONE

// Pre condition:  number > 2
// Post condition: Return false when the number is not prime 
//                 or return true when the number is prime
bool isPrime(int number);   //   DONE

// Pre condition:  NONE
// Post condition: Return the number if the number is prime
//                 it asks for a new number utill it gets a prime number
//                 it does NOT crashes for non-numeric input
//                 it checks the number by using isPime function
int getPrime();

// Pre condition:  number > 0
// Post condition: Return a integer value  
//                 which is used to select class of the number
//                 if return -1 when the number is deficient
//                 if return 0 when the number is perfect
//                 if return 1 when the number is abundant
int classifiesNumber(int number);

// Pre condition:  NONE
// Post condition: Return a integer value  
//                 it checks the number that a user is integer or not
//                 it does NOT crashes for non-numeric input
//                 removes everything else from the cin
int getInteger();     //  DONE

// Pre condition:  1 <= line, but line <= 4
// Post condition: Print the ASCII table in columns n line 
void printASCIITable(int line);     //  DONE

// Pre condition:  number is a integer number 
// Post condition: Return a integer value
//                 it checks the number that a user is bigger the a number or not
//                 it does NOT crashes for non-numeric input
//                 removes everything else from the cin
int getIntBiggerThan(int number);

// Pre condition:  NONE
// Post condition: Return a valid double number
//                 it crashes for non-numeric input
//                 removes everything else from the cin
double getNum();     //  DONE

