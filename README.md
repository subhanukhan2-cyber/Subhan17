experiment 1 
#include <stdio.h>

int main() {
    float physics, chemistry, maths, total, average;

    printf("Enter marks for Physics: ");
    scanf("%f", &physics);

    printf("Enter marks for Chemistry: ");
    scanf("%f", &chemistry);

    printf("Enter marks for Mathematics: ");
    scanf("%f", &maths);

    total = physics + chemistry + maths;
    average = total / 3.0;

    printf("\n------------------------------\n");
    printf("PCM Total: %.2f / 300\n", total);
    printf("Average Marks: %.2f%%\n", average);
    printf("------------------------------\n");

    printf("Status: %s\n",
        (average >= 50) ? "ELIGIBLE for Admission" :
        "NOT ELIGIBLE for Admission");

    return 0;
}
experiment 2

#include <stdio.h>

int main() {
    int num;

    printf("Enter an integer: ");
    scanf("%d", &num);

    if (num % 2 == 0)
        printf("%d is Even\n", num);
    else
        printf("%d is Odd\n", num);

    return 0;


}



experiment 3



#include <stdio.h>

int main() {
    int start, end, i, temp, sum = 0;

    printf("Enter two numbers: ");
    scanf("%d %d", &start, &end);

    if (start > end) {
        temp = start;
        start = end;
        end = temp;
    }

    for (i = start; i <= end; i++) {
        if (i % 2 != 0)
            sum = sum + i;
    }

    printf("Sum of odd numbers = %d\n", sum);

    return 0;
}




experiment 4
#include <stdio.h>

int main() {
    int choice;
    float m1, m2, m3, total, avg;
    char continue_choice;

main_menu:
    printf("\n=========================================\n");
    printf(" STUDENT GRADE & RESULT MANAGEMENT \n");
    printf("=========================================\n");
    printf("1. Calculate Total and Average Marks\n");
    printf("2. Determine Student Grade\n");
    printf("3. Check Pass/Fail Result Status\n");
    printf("4. Exit Program\n");
    printf("-----------------------------------------\n");
    printf("Enter your choice (1 to 4) : ");

    if (scanf("%d", &choice) != 1) {
        printf("Invalid input! Please enter a valid integer.\n");
        return 1;
    }

    switch (choice) {
        case 1:
            printf("\n--- Total & Average Calculation ---\n");
            printf("Enter marks for 3 subjects (out of 100): ");
            scanf("%f %f %f", &m1, &m2, &m3);

            if (m1 < 0 || m1 > 100 ||
                m2 < 0 || m2 > 100 ||
                m3 < 0 || m3 > 100) {
                printf("Error: Marks must be between 0 and 100.\n");
            } else {
                total = m1 + m2 + m3;
                avg = total / 3.0;

                printf("Total Marks: %.2f / 300\n", total);
                printf("Average Percentage: %.2f%%\n", avg);
            }
            break;

        case 2:
            printf("\n--- Grade Determination ---\n");
            printf("Enter average percentage: ");
            scanf("%f", &avg);

            if (avg < 0 || avg > 100)
                printf("Invalid percentage entered.\n");
            else if (avg >= 85)
                printf("Grade: O (Outstanding)\n");
            else if (avg >= 75)
                printf("Grade: A+ (Excellent)\n");
            else if (avg >= 65)
                printf("Grade: A (Very Good)\n");
            else if (avg >= 55)
                printf("Grade: B+ (Good)\n");
            else if (avg >= 50)
                printf("Grade: B (Above Average)\n");
            else if (avg >= 40)
                printf("Grade: C (Pass)\n");
            else
                printf("Grade: F (Fail)\n");
            break;

        case 3:
            printf("\n--- Pass/Fail Result Status ---\n");
            printf("Enter marks for 3 subjects: ");
            scanf("%f %f %f", &m1, &m2, &m3);

            if (m1 < 40 || m2 < 40 || m3 < 40)
                printf("Result: FAIL (Scored below passing mark 40 in one or more subjects)\n");
            else
                printf("Result: PASS\n");
            break;

        case 4:
            printf("\nExiting the system. Thank you!\n");
            goto exit_program;

        default:
            printf("\nInvalid Choice! Please select an option between 1 and 4.\n");
    }

    printf("\nDo you want to perform another operation? (y/n): ");
    scanf(" %c", &continue_choice);

    if (continue_choice == 'y' || continue_choice == 'Y')
        goto main_menu;

exit_program:
    return 0;
}





experiment 5
#include <stdio.h>

// Recursive function to find the nth Fibonacci number
int fibonacci_recursive(int n) {
    if (n <= 1) {
        return n;
    }

    return fibonacci_recursive(n - 1) +
           fibonacci_recursive(n - 2);
}

// Iterative function to generate Fibonacci series
void fibonacci_iterative(int n) {
    int t1 = 0, t2 = 1, nextTerm;

    printf("Iterative Fibonacci Series: ");

    for (int i = 1; i <= n; ++i) {
        printf("%d ", t1);

        nextTerm = t1 + t2;
        t1 = t2;
        t2 = nextTerm;
    }

    printf("\n");
}

int main() {
    int n;

    printf("Enter the number of terms: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("Please enter a positive integer.\n");
        return 0;
    }

    fibonacci_iterative(n);

    printf("Recursive Fibonacci Series: ");

    for (int i = 0; i < n; i++) {
        printf("%d ", fibonacci_recursive(i));
    }

    printf("\n");

    return 0;
}




experiment 6 
#include <stdio.h>

// Function using a static storage class variable
void counterFunction() {
    static int count = 0;

    count++;

    printf("Function called %d time(s).\n", count);
}

int main() {
    int n, i;

    printf("Enter how many times you want to call the counter function: ");
    scanf("%d", &n);

    printf("\n--- Calling Counter Function ---\n");

    for (i = 0; i < n; i++) {
        counterFunction();
    }

    return 0;
}







