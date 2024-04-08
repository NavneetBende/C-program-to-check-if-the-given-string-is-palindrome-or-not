Check whether a String is a Palindrome
Today in this article we will learn how to check whether a String is a Palindrome using C++ Programming language. Different methods to write String Palindrome Program in C++

A string is palindrome if the reverse and the original string is same

Lets understand this with the help of an example:- 

Input sting:- AMA
Reverse sting:- AMA
Here AMA = AMA so this is a palindrome 

Check whether a String is Palindrome
Algorithm:
Initialize the variable.
Accept the input.
Initialize for loop.
Check if string is palindrome or not.
Terminate for loop.
Print result.
Check whether a String is Palindrome in Cpp
Method 1: C++ programming code to check if a given string is palindrome or not
Run
// String palindrome program in c++
#include <iostream>
#include <stdio.h> 
using namespace std;
void Lower_case(char str[]){
    int i = 0;
    while (str[i] != '\0')
    {
        if (str[i] > 64 && str[i] < 91)
            str[i] += 32;
        i++;
    } 
}
// A function to check if a string str is palindrome
void CheckPalindrome(char str[]) {
// Start from leftmost and rightmost corners of str
int l = 0;
int h = strlen(str) - 1;

// Keep comparing characters while they are same
Lower_case(str);

while (h > l) {  
      if (str[l++] != str[h--]) { 
           cout << "The String " << str << " is not a palindrome\n";           
 return;      
  }   
 }    
cout << "The String " << str << " is a palindrome"; 
}
// Driver program to test CheckPalindrome function int main() {    
char str1[50] = "naman";  // size of char string    
CheckPalindrome(str1);
cout<<endl;
char str2[50] = "radar";  // size of char string    
CheckPalindrome(str2);
return 0; 
}
Output
The String naman is a palindrome
The String radar is a palindrome
Note
In this C++ program to check a string is a palindrome or not we will iterate first half of the string through a for loop and will compare it with remaining half as we need to find if first and last, second and second last, and so in the string are equal or not. If these characters are equal then the string is palindrome else it is not.
Related Pages
Juggling algorithm for array rotation
 
Balanced Parenthesis Problem
 
Toggle each character in a string

Find the ASCII value of a character

Length of the string without using strlen() function

Prime Course Trailer

Related Banners
Get PrepInsta Prime & get Access to all 200+ courses offered by PrepInsta in One Subscription

Get Prime
Method 2
We can also Check whether a String is Palindrome with another method given below:-

The approach is to transfer the string to another string in a reverse manner let the another array is rev.
All we need is the size of the string.
The method is to initialize a character array of the equal size and start copying the elements of the input string from the end.
And then check the rev and the original string and if both are same then its is palindrome else its not palindrome
Run
#include <iostream>
#include <stdio.h>
using namespace std;
void Lower_case(char str[]) {
    int i = 0;
    while (str[i] != '\0') {
        if (str[i] > 64 && str[i] < 91) str[i] += 32;
        i++;
    }
}
int main() {
    char str[10] = "nAman", rev[1000];
    int i, j, count = 0;
    cout << "String Before Reverse: " << str << endl;
    // finding the length of the string
    while (str[count] != '\0') {
        count++;
    }
    j = count - 1;
    Lower_case(str);
    // reversing the string by storing it in another array
    for (i = 0; i <= count; i++) {
        rev[i] = str[j];
        j--;
    }
    cout << "String After Reverse:" << rev << endl;
    int res = strcmp(str, rev);
    if (res == 0) {
        cout << str << " is Palindrome";
    } else {
        cout << str << " Not palindorme";
    }
    return 0;
}
Output
String Before Reverse: nAman
String After Reverse:naman
naman is Palindrome
