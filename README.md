# Adithi-Alva's-Institute-of-Engineering-and-Technology


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
