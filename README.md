# Subtask-2-ISAT
#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>
#include <cctype>
using namespace std;
string decimalToBinary(int decimal)
{
    if (decimal == 0)
        return "0";
    string binary = "";
    while (decimal > 0)
    {
        int remainder = decimal % 2;
        if (remainder == 0)
            binary = "0" + binary;
        else
            binary = "1" + binary;
        decimal = decimal / 2;
    }
    return binary;
}
int binaryToDecimal(string binary)
{
    int decimal = 0;
    for (int i = 0; i < binary.length(); i++)
    {
        decimal = decimal * 2 + (binary[i] - '0');
    }
    return decimal;
}
string decimalToHexadecimal(int decimal)
{
    if (decimal == 0)
        return "0";
    string hexadecimal = "";
    string digits = "0123456789ABCDEF";
    while (decimal > 0)
    {
        int remainder = decimal % 16;
        hexadecimal = digits[remainder] + hexadecimal;
        decimal = decimal / 16;
    }
    return hexadecimal;
}
int hexadecimalToDecimal(string hexadecimal)
{
    int decimal = 0;
    for (int i = 0; i < hexadecimal.length(); i++)
    {
        char digit = toupper(hexadecimal[i]);
        int value;
        if (digit >= '0' && digit <= '9')
value = digit - '0';
        else
            value = digit - 'A' + 10;
        decimal = decimal * 16 + value;
    }
    return decimal;
}
void demo()
{
    int number = rand() % 100;
    cout << "\n--- DEMO ---" << endl;
    cout << "Random decimal number: " << number << endl;
    cout << "Binary equivalent: "
         << decimalToBinary(number) << endl;
}
int main()
{
    srand(time(0));
    int choice;
    int decimal;
    string binary;
    string hexadecimal;
    do
    {
        cout << "\n====================================";
        cout << "\n     NUMBER CONVERSION 
       PROGRAM";
        cout << "\n====================================";
        cout << "\n1. Convert Decimal to Binary";
        cout << "\n2. Convert Binary to Decimal";
        cout << "\n3. Convert Decimal to Hexadecimal";
        cout << "\n4. Convert Hexadecimal to Decimal";
        cout << "\n5. Demo";
        cout << "\n6. Exit";
        cout << "\n====================================";
        cout << "\nEnter your choice: ";
        cin >> choice;
        switch (choice)
        {
            case 1:
                cout << "\nEnter a decimal number: ";
                cin >> decimal;
                cout << "Binary: "
                     << decimalToBinary(decimal) << endl;
                break;
            case 2:
                cout << "\nEnter a binary number: ";
                cin >> binary;
                cout << "Decimal: "
                     << binaryToDecimal(binary) << endl;
                break;
            case 3:
                cout << "\nEnter a decimal number: ";
                cin >> decimal;
                cout << "Hexadecimal: "
                     << decimalToHexadecimal(decimal) << endl;
                break;
            case 4:
                cout << "\nEnter a hexadecimal number: ";
                cin >> hexadecimal;
                cout << "Decimal: "
                     << hexadecimalToDecimal(hexadecimal) << endl;
                break;
            case 5:
                demo();
                break;
            case 6:
                cout << "\nProgram ended." << endl;
                break;
            default:
 cout << "\nInvalid choice. Please try again."
                     << endl;
        }
    } while (choice != 6);
    return 0;
} 
