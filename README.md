# CODING
#include <iostream>
#include <cmath>
#include <algorithm>
#include <vector>
#include <string>

using namespace std;

void numberLogic(int n) {
    int original = n, reversed = 0, count = 0, sum = 0;
    
    // Count Digits & Reverse & Armstrong Logic
    int temp = n;
    int digits = floor(log10(n) + 1); // Fast way to count digits

    while (temp > 0) {
        int lastDigit = temp % 10;
        reversed = reversed * 10 + lastDigit;
        sum += pow(lastDigit, digits); // For Armstrong
        temp /= 10;
        count++;
    }

    cout << "Reversed: " << reversed << endl;
    cout << "Digit Count: " << count << endl;
    cout << "Is Palindrome: " << (original == reversed ? "Yes" : "No") << endl;
    cout << "Is Armstrong: " << (original == sum ? "Yes" : "No") << endl;
}
