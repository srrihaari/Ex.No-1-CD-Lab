# Ex. No : 1

# IMPLEMENTATION OF SYMBOL TABLE

# Register Number : 212223040202

# Name : SRI HARI R

# Date: 25/8/2025

# AIM:

To write a C program to implement a symbol table.

# ALGORITHM:

1. Start the program.
2. Get the input from the user with the terminating symbol ‘$’.
3. Allocate memory for the variable by dynamic memory allocation function.
4. If the next character of the symbol is an operator then only the memory is allocated.
5. While reading, the input symbol is inserted into symbol table along with its memory address.
6. The steps are repeated till ‘$’ is reached.
7. To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8. Stop the program.

# PROGRAM:
#include <stdio.h>
#include <ctype.h>
#include <string.h>
#include <stdlib.h>

#define MAX_EXPRESSION_SIZE 100

int main() {
    int i = 0, j = 0, x = 0, n, flag = 0;
    void *add[15];   // increased size for safety
    char b[MAX_EXPRESSION_SIZE], d[15], c, srch;

    // Input expression
    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0';
    n = i - 1;

    printf("Given Expression: %s\n", b);

    // Print header
    printf("\nSymbol Table\n");
    printf("Symbol\taddr\ttype\n");

    // Build symbol table
    for (j = 0; j <= n; j++) {
        c = b[j];
        if (isalpha((unsigned char)c)) {
            // allocate memory for identifier
            void *p = malloc(sizeof(char));
            add[x] = p;
            d[x] = c;
            printf("%c\t%p\tidentifier\n", c, p);
            x++;
        }
    }

    // Search symbol
    printf("\nThe symbol to be searched: ");
    while ((srch = getchar()) == '\n');   // skip newline

    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol Found\n");
            printf("%c@address%p\n", srch, add[i]);
            flag = 1;
            break;
        }
    }

    if (flag == 0)
        printf("Symbol Not Found\n");

    // Free allocated memory
    for (i = 0; i < x; i++) {
        free(add[i]);
    }

    return 0;
}

# OUTPUT:
<img width="751" height="459" alt="Screenshot 2025-08-24 193100" src="https://github.com/user-attachments/assets/feb16887-991e-43d5-be66-1ea463d10398" />

<img width="903" height="401" alt="Screenshot 2025-08-24 193142" src="https://github.com/user-attachments/assets/be882d43-768e-41cb-9277-7f49aaf16613" />



# RESULT:

The program to implement a symbol table is executed and the output is verified.
