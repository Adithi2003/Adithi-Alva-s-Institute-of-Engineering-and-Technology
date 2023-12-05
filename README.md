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
