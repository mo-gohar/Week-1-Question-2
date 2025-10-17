# Week-1-Question-2
#include <stdio.h>

int main() {
    char op;
    double num1, num2, result;
    int valid = 0; 

    do {
        printf("Enter an operator (+, -, *, /): ");
        scanf(" %c", &op);

        if (op != '+' && op != '-' && op != '*' && op != '/') {
            printf("Invalid operator! Please enter one of (+, -, *, /).\n\n");
            continue; 
        }

        printf("Enter two numbers: ");
        if (scanf("%lf %lf", &num1, &num2) != 2) {
            printf("Invalid numbers! Please enter numeric values.\n\n");

            while (getchar() != '\n');
            continue;
        }

        switch (op) {
            case '+':
                result = num1 + num2;
                printf("Result: %.2lf\n", result);
                valid = 1;
                break;

            case '-':
                result = num1 - num2;
                printf("Result: %.2lf\n", result);
                valid = 1;
                break;

            case '*':
                result = num1 * num2;
                printf("Result: %.2lf\n", result);
                valid = 1;
                break;

            case '/':
                if (num2 == 0) {
                    printf("Error: Division by zero is not allowed.\n\n");
                    continue;
                }
                result = num1 / num2;
                printf("Result: %.2lf\n", result);
                valid = 1;
                break;
        }

    } while (!valid);

    printf("Calculation completed successfully.\n");
    return 0;
}
