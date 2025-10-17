
// scientific-calculator
#include <stdio.h>
#include <math.h>

// Function declarations
double add(double a, double b);
double subtract(double a, double b);
double multiply(double a, double b);
double divide(double a, double b);
double power(double base, double exp);
long long factorial(int n);
double squareRoot(double n);

int main() {
    int choice;
    double num1, num2, result;
    int n;

    while (1) {
        printf("\n===== SCIENTIFIC CALCULATOR =====\n");
        printf("1. Addition\n");
        printf("2. Subtraction\n");
        printf("3. Multiplication\n");
        printf("4. Division\n");
        printf("5. Power\n");
        printf("6. Factorial\n");
        printf("7. Square Root\n");
        printf("8. Exit\n");
        printf("Choose an operation (1-8): ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter two numbers: ");
                scanf("%lf %lf", &num1, &num2);
                result = add(num1, num2);
                printf("Result: %.2lf\n", result);
                break;

            case 2:
                printf("Enter two numbers: ");
                scanf("%lf %lf", &num1, &num2);
                result = subtract(num1, num2);
                printf("Result: %.2lf\n", result);
                break;

            case 3:
                printf("Enter two numbers: ");
                scanf("%lf %lf", &num1, &num2);
                result = multiply(num1, num2);
                printf("Result: %.2lf\n", result);
                break;

            case 4:
                printf("Enter two numbers: ");
                scanf("%lf %lf", &num1, &num2);
                if (num2 == 0)
                    printf("Error: Division by zero is not allowed.\n");
                else {
                    result = divide(num1, num2);
                    printf("Result: %.2lf\n", result);
                }
                break;

            case 5:
                printf("Enter base and exponent: ");
                scanf("%lf %lf", &num1, &num2);
                result = power(num1, num2);
                printf("Result: %.2lf\n", result);
                break;

            case 6:
                printf("Enter a positive integer: ");
                scanf("%d", &n);
                if (n < 0)
                    printf("Error: Factorial of negative number not defined.\n");
                else
                    printf("Result: %d! = %lld\n", n, factorial(n));
                break;

            case 7:
                printf("Enter a number: ");
                scanf("%lf", &num1);
                if (num1 < 0)
                    printf("Error: Square root of negative number not possible.\n");
                else
                    printf("Result: %.2lf\n", squareRoot(num1));
                break;

            case 8:
                printf("Exiting calculator. Goodbye!\n");
                return 0;

            default:
                printf("Invalid choice! Please choose between 1�8.\n");
        }
    }

    return 0;
}

// Function definitions
double add(double a, double b) {
    return a + b;
}

double subtract(double a, double b) {
    return a - b;
}

double multiply(double a, double b) {
    return a * b;
}

double divide(double a, double b) {
    return a / b;
}

double power(double base, double exp) {
    return pow(base, exp);
}

long long factorial(int n) {
    if (n == 0 || n == 1)
        return 1;
    else
        return n * factorial(n - 1);
}

double squareRoot(double n) {
    return sqrt(n);
}


