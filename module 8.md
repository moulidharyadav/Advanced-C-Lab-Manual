EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
```
#include <stdio.h>
int main() {
    int number;
    printf("Enter a number (1-9): ");
    scanf("%d", &number);
    switch (number) {
        case 1:
            printf("one\n");
            break;
        case 2:
            printf("two\n");
            break;
        case 3:
            printf("three\n");
            break;
        case 4:
            printf("four\n");
            break;
        case 5:
            printf("five\n");
            break;
        case 6:
            printf("six\n");
            break;
        case 7:
            printf("seven\n");
            break;
        case 8:
            printf("eight\n");
            break;
        case 9:
            printf("nine\n");
            break;
        default:
            printf("number is not in range 1-9\n");
    }
    return 0;
}
```


Output:


![image](https://github.com/user-attachments/assets/5a6ef109-4c01-4d31-b19b-5fa4f21aa85c)






Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
```
#include <stdio.h>
int main() {
    int count[4] = {0};
    char ch;
    printf("Enter a string of digits (0-9): ");
    while ((ch = getchar()) != '\n') {
        if (ch >= '0' && ch <= '3') {
            count[ch - '0']++;
        }
    }
    for (int i = 0; i < 4; i++) {
        printf("%d ", count[i]);
    }
    printf("\n");
    return 0;
}

```


Output:


![image](https://github.com/user-attachments/assets/1a9bdc96-14ac-49dd-80e2-15afe75c47ff)






Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}
int cmp(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}
int next_permutation(char **s, int n) {
    int i = n - 2;
    while (i >= 0 && strcmp(s[i], s[i + 1]) >= 0)
        i--;
    if (i < 0)
        return 0;
    int j = n - 1;
    while (strcmp(s[j], s[i]) <= 0)
        j--;
    swap(&s[i], &s[j]);
    int start = i + 1, end = n - 1;
    while (start < end) {
        swap(&s[start], &s[end]);
        start++;
        end--;
    }
    return 1;
}
int main() {
    int n;
    char **s;
    printf("Enter the number of strings: ");
    scanf("%d", &n);
    s = (char **)malloc(n * sizeof(char *));
    if (s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }
    for (int i = 0; i < n; i++) {
        s[i] = (char *)malloc(100 * sizeof(char));
        if (s[i] == NULL) {
            printf("Memory allocation failed for string %d.\n", i);
            return 1;
        }
        printf("Enter string %d: ", i + 1);
        scanf("%s", s[i]);
    }
    qsort(s, n, sizeof(char *), cmp);
    do {
        for (int i = 0; i < n; i++) {
            printf("%s ", s[i]);
        }
        printf("\n");
    } while (next_permutation(s, n));
    for (int i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);
    return 0;
}

```


Output:


![image](https://github.com/user-attachments/assets/45808a2e-7ae0-4377-a398-08678a3e49af)






Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
```
#include <stdio.h>
int main() {
    int n, i, j, min;
    printf("Enter a number (n): ");
    scanf("%d", &n);
    int len = n * 2 - 1;
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            int top = i;
            int left = j;
            int right = len - 1 - j;
            int bottom = len - 1 - i;
            min = top;
            if (left < min) min = left;
            if (right < min) min = right;
            if (bottom < min) min = bottom;
            printf("%d ", n - min);
        }
        printf("\n");
    }
    return 0;
}

```


Output:


![image](https://github.com/user-attachments/assets/e2259212-788b-46b4-b741-a648cd675314)






Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:
```
#include <stdio.h>
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}
int main() {
    int result;
    result = square();
    printf("Square of the number is: %d\n", result);
    return 0;
}

```


Output:


![image](https://github.com/user-attachments/assets/7b347c43-055a-47cd-9bd1-eb23d4973373)






Result:
Thus, the program is verified successfully



























