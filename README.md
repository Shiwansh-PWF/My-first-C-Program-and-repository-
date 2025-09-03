# 📝 Understanding My C Program 1.5

---
```
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

```
## 1. **Header File**

`#include <stdio.h>`

- This line tells the compiler to include the **Standard Input/Output library**.
    
- Functions like `printf`, `scanf`, and `getchar` come from this library.
    
- Without it, the program wouldn’t know how to print messages or read user input.
    

---

## 2. **Main Function**

`int main() {`

- Every C program starts running from `main()`.
    
- It returns an `int` because, by convention, returning `0` means the program ended successfully.
    

---

## 3. **Variable Declarations**

`int a, b; int result; char reset;`

- `a` and `b` → store the two integers the user will input.
    
- `result` → stores the return value of `scanf`. (This helps us check if the user really entered an integer.)
    
- `reset` → stores a character that decides if the program should repeat (`r`/`R`) or quit.
    

---

## 4. **The Loop**

`do {     ... } while (reset == 'r' || reset == 'R');`

- A **do–while loop** always runs at least once.
    
- After each run, the program asks the user: _“Do you want to run again?”_
    
- If the user types `r` or `R`, the loop repeats.
    
- Any other input ends the program.
    

---

## 5. **Input for `a`**

`printf("Enter the value for a: "); while ((result = scanf("%d", &a)) != 1) {     printf("Invalid input! Please enter an integer: ");     while (getchar() != '\n');  // clear wrong input }`

- `printf` shows a message asking for `a`.
    
- `scanf("%d", &a)` tries to read an integer.
    
- If the user types something invalid (like `"abc"`), then `scanf` will not return `1`.
    
- The `while` loop keeps asking until the input is valid.
    
- `while (getchar() != '\n');` clears leftover characters (like letters) from the input buffer.
    

👉 This ensures the program **only accepts integers**.

---

## 6. **Input for `b`**

`printf("Enter the value for b: "); while ((result = scanf("%d", &b)) != 1) {     printf("Invalid input! Please enter an integer: ");     while (getchar() != '\n');  // clear wrong input }`

- Works the same way as for `a`.
    
- This guarantees both `a` and `b` are integers before moving on.
    

---

## 7. **Checking Conditions**

`if (a < 0)     printf("a (%d) is negative\n", a);  if (b < 0)     printf("b (%d) is negative\n", b);  if (a > 0 && b > 0)     printf("Neither value is negative\n");  if (a == 0 && b == 0)     printf("Both the values are zero\n");`

- Each `if` statement checks a condition:
    
    - If `a` is less than 0 → print that `a` is negative.
        
    - If `b` is less than 0 → print that `b` is negative.
        
    - If both are greater than 0 → print that neither is negative.
        
    - If both are zero → print a special message.
        

⚡ Notice: Multiple `if`s can run here (they’re not `else if`).  
Example: If `a = 0` and `b = 0`, the last condition triggers.

---

## 8. **Showing the Values**

`printf("a = %d, b = %d\n", a, b);`

- Prints both values for clarity.
    
- `%d` is the placeholder for integers.
    

---

## 9. **Asking to Repeat**

`printf("Press 'r' or 'R' to run again, any other key to quit: "); while (getchar() != '\n');  // clear leftover newline scanf("%c", &reset);`

- Asks the user if they want to repeat.
    
- `while (getchar() != '\n');` clears the **newline character** left over from the last `scanf`.
    
- `scanf("%c", &reset);` reads a single character into `reset`.
    
- Next loop cycle checks if it’s `'r'` or `'R'`.
    

---

## 10. **End of Program**

`return 0;`

- Ends the program with success.
