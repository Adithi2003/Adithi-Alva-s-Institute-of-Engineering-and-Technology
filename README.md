# Adithi-Alva's-Institute-of-Engineering-and-Technology

Easy
Given a string s consisting of words and spaces, return the length of the last word in the string.
A word is a maximal 
substring consisting of non-space characters only


#include <stdio.h>
#include <string.h>

int lengthOfLastWord(const char *str) {
    int length = 0;
    int i = strlen(str) - 1;

    while (i >= 0 && str[i] == ' ') {
        i--;
    }

    while (i >= 0 && str[i] != ' ') {
        length++;
        i--;
    }

    return length;
}

int main() {
    char input[100];

    printf("Enter a string: ");
    fgets(input, sizeof(input), stdin);

    input[strcspn(input, "\n")] = '\0';

    printf(" %d\n", lengthOfLastWord(input));
    return 0;
}



Description:
When we type a, it figures out the length of the last word that we write. First, it gets rid of any extra spaces we might have put in our input. Then, it starts at the end of what we wrote and ignores any empty spaces. After that, it counts the letters until it reaches another space or the beginning of our input. Finally, it tells us how many letters are in that last word. So, if we type in something like "Hello world," it will say that the last word,i.e., "world," has five letters.

*****************************************************************8
Medium 2 

Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.

#include <stdio.h>

void findMajElements(int nums[], int n) {
    if (n == 0) {
        return;
    }

    
    int candidate1 = nums[0], count1 = 1;
    int candidate2 = 0, count2 = 0;

    for (int i = 1; i < n; i++) {
        if (nums[i] == candidate1) {
            count1++;
        } else if (nums[i] == candidate2) {
            count2++;
        } else if (count1 == 0) {
            candidate1 = nums[i];
            count1 = 1;
        } else if (count2 == 0) {
            candidate2 = nums[i];
            count2 = 1;
        } else {
            count1--;
            count2--;
        }
    }

  
    count1 = 0;
    count2 = 0;

   
    for (int i = 0; i < n; i++) {
        if (nums[i] == candidate1) {
            count1++;
        } else if (nums[i] == candidate2) {
            count2++;
        }
    }

    if (count1 > n / 3) {
        printf("%d ", candidate1);
    }
    if (count2 > n / 3 && candidate1 != candidate2) {
        printf("%d ", candidate2);
    }
}

int main() {
   
    int n;
    printf("Enter the size of the array: ");
    scanf("%d", &n);

    int nums[n];
    printf("Enter the elements of the array, separated by spaces:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &nums[i]);
    }

    printf("Output: ");
    findMajorityElements(nums, n);

    return 0;
}


Description:

This program helps you find numbers in a list that show up more than a third of the time. It does this by looking at the list and picking two potential candidates for frequently occurring numbers. It then checks how often these candidates actually appear, and if either appears more than a third of the time, the program tells you what those numbers are. The program asks you for the size of your list and the numbers in it, and then it gives you the result based on its analysis.

***********************************************************************************
Hard 3
Given an integer n, count the total number of digit 1 appearing in all non-negative integers less than or equal to n.
#include <stdio.h>
#include<math.h>
int countDigitOne(int n) {
    int count = 0;

    for (int i = 1; i <= n; i *= 10) {
        int divisor = i * 10;
        count += (n / divisor) * i + fmin(fmax(n % divisor - i + 1, 0), i);
    }

    return count;
}

int main() {
    int n;

   
    printf("Enter a non-negative integer (n): ");
    scanf("%d", &n);

  
    printf("The total number of digit 1 from 1 to %d is: %d\n", n, countDigitOne(n));

    return 0;
}
Description:
The countDigitOne function in this C program  for every digit place, it computes how frequently the digit 1 appears across all numbers in that range. The final count is determined by summing up these individual counts for each digit place. In the main function, user input for the value of n is received, and the countDigitOne function is invoked to efficiently calculate and display the total occurrences of the digit 1 within the specified range of non-negative integers.
