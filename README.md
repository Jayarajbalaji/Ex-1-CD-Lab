# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol and memory address are inserted into the symbol table.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and the symbol table has been checked for the corresponding variable, the variable along with its address is displayed as a result.
8.	Stop the program. 
# PROGRAM
```
#include <stdio.h>
#include <ctype.h>

#define MAX_EXPRESSION_SIZE 100
#define MAX_SYMBOLS 15

int main() {
    int i = 0, j, x = 0, flag = 0;
    char b[MAX_EXPRESSION_SIZE];
    char d[MAX_SYMBOLS], c, srch;

    printf("Enter the Expression terminated by $: ");

    while ((c = getchar()) != '$' &&
           c != EOF && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }

    b[i] = '\0';

    printf("\nGiven Expression: %s\n", b);

    printf("\nSymbol Table\n");
    printf("Symbol\tType\t\tAddress\n");

    for (j = 0; j < i; j++) {
        c = b[j];

        if (isalpha((unsigned char)c)) {
            int alreadyExists = 0;

            for (int k = 0; k < x; k++) {
                if (d[k] == c) {
                    alreadyExists = 1;
                    break;
                }
            }

            if (!alreadyExists && x < MAX_SYMBOLS) {
                d[x] = c;

                printf("%c\tidentifier\t%p\n",
                       c, (void *)&d[x]);

                x++;
            }
        }
    }

    printf("\nEnter the symbol to search: ");
    scanf(" %c", &srch);

    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            flag = 1;
            break;
        }
    }

    if (flag == 1)
        printf("Symbol Found\n");
    else
        printf("Symbol Not Found\n");

    return 0;
}
```


# OUTPUT
Symbol Found

<img width="1186" height="610" alt="image" src="https://github.com/user-attachments/assets/f5a3d76e-b81d-4a33-aa67-6cfc514a3b30" />


Symbol Not Found

<img width="1177" height="604" alt="image" src="https://github.com/user-attachments/assets/94b69265-b2aa-4147-b147-aff0cc410243" />

# RESULT
### The program to implement a symbol table is executed and the output is verified.
