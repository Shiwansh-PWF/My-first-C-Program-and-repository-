# My-first-C-Program-and-repository-
I am currently 3 lectures deep into programming in c and i created this simple program which tells me the nature of integer whether its negative, positive or zero 

Here is the entire code:

    #include <stdio.h>
     int main() {
     int a, b;
     int result;
     char reset;
    do {
        // Input for a
        printf("Enter the value for a: ");
        while ((result = scanf("%d", &a)) != 1) {
            printf("Invalid input! Please enter an integer: ");
            while (getchar() != '\n');  // clear wrong input
        }

        // Input for b
        printf("Enter the value for b: ");
        while ((result = scanf("%d", &b)) != 1) {
            printf("Invalid input! Please enter an integer: ");
            while (getchar() != '\n');  // clear wrong input
        }

        // Conditions
        if (a < 0)
            printf("a (%d) is negative\n", a);
        if (b < 0)
            printf("b (%d) is negative\n", b);
        if (a > 0 && b > 0)
            printf("Neither value is negative\n");
        if (a == 0 && b == 0)
            printf("Both the values are zero\n");

        // Show final values
        printf("a = %d, b = %d\n", a, b);

        // Ask user if they want to run again
        printf("Press 'r' or 'R' to run again, any other key to quit: ");
        while (getchar() != '\n');  // clear leftover newline
        scanf("%c", &reset);

    } while (reset == 'r' || reset == 'R');

    return 0;
}
