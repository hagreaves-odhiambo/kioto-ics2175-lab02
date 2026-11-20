# ICS 2175 – Laboratory 02 Report

## 1. Cover Information
- **Student Full Name:** HAGREAEVES ODHIAMBO
- **Registration Number:** ENB211-0061/2025
- **Programme:** BSc. Agricultural and Biosystems Engineering
- **Unit:** ICS 2175 – Introduction to Computer Programming
- **Lab Number:** Laboratory 02 – Selection and Decision-Making
- **GitHub Username:** hagreaves-odhiambo
- **Date:** November 20, 2026

## 2. Objective
The objective of this laboratory was to learn how to control program flow in C using decision-making structures. Specifically, I aimed to apply relational and logical operators to evaluate conditions, implement `if / else-if / else` ladders and `switch` statements to classify student marks into grades (A–F) and Pass/Fail statuses, handle input validation and boundary values, and submit the completed work using a professional Git and GitHub fork-and-pull-request workflow.

## 3. Environment and Setup
- **Operating System:** Windows 11 (64-bit)
- **IDE:** Code::Blocks 20.03
- **Compiler / Toolchain:** GNU GCC Compiler (MinGW)
- **Version Control Tools:** Git & GitHub Desktop

## 4. Exercise — Selection

### Source Code
```c
#include <stdio.h>
#include <stdlib.h>
/*
Mark range	Grade	Status
80 – 100	A	    Pass
70 – 79	    B	    Pass
60 – 69	    C	    Pass
50 – 59	    D	    Pass
0 – 49	    F	    Fail
*/

int main()
{
    int mark;
    printf("Enter the score : \n");
    scanf("%d", &mark);
    if (mark < 0 || mark > 100){
         printf("Invalid mark. Please enter a value between 0 and 100.\n");
        return 1;
    if (mark >=80){
        printf("Grade: A\n");
    }
    else if (mark >= 70){
        printf("Grade: B\n");
    }
    else if (mark >= 60){
        printf("Grade: C\n");
    }
    else if (mark >= 50){
        printf("Grade: D\n");
    }
    else{
        printf("Grade: F\n");
    }
    return 0;
```


### Explanation of Key Statements
- **Input Validation (`if (mark < 0 || mark > 100)`):** Uses relational operators (`<`, `>`) and the logical OR operator (`||`) to catch invalid numbers before grading begins.
- **`if / else-if / else` Ladder:** Evaluates conditions sequentially from highest to lowest (`>= 80` down to `< 50`). Once a condition evaluates to true, its block runs and the remaining branches are skipped.
- **Pass/Fail Block (`if (mark >= 50)`):** Uses a two-way `if-else` decision to print `Pass` for marks of 50 and above, and `Fail` for marks below 50.

### Program Output
- **Test Case 1 (`85`):** Output -> `Grade: A`, `Status: Pass`
- **Test Case 2 (`72`):** Output -> `Grade: B`, `Status: Pass`
- **Test Case 3 (`40`):** Output -> `Grade: F`, `Status: Fail`

<img width="1366" height="768" alt="Screenshot 2026-11-20 171647" src="https://github.com/user-attachments/assets/bb4a9997-63c7-43c6-89fc-508887db6161" />

<img width="1366" height="768" alt="Screenshot 2026-11-20 173847" src="https://github.com/user-attachments/assets/bec052ac-1f70-48b0-8509-d8589838d83f" />
<img width="1365" height="768" alt="Screenshot 2026-11-20 173945" src="https://github.com/user-attachments/assets/56922dab-844e-4554-b258-70a39a113772" />
<img width="1366" height="768" alt="Screenshot 2026-11-20 173740" src="https://github.com/user-attachments/assets/c3eedad7-010a-4850-908a-42a3d3fa924d" />
<img width="1366" height="768" alt="Screenshot 2026-11-20 173816" src="https://github.com/user-attachments/assets/75df1258-6697-4f80-bf2a-76d605d1dca5" />


## 5. Testing and Troubleshooting
- **Boundary & Invalid Value Testing:** I tested the exact grade cutoffs (`0`, `49`, `50`, `59`, `60`, `69`, `70`, `79`, `80`, `100`) as well as invalid numbers (`-5` and `105`).
- **Error Encountered & Fix:** Initially, entering `-5` printed `Grade: F` and `Status: Fail` because `-5` satisfied the final `else` block, and entering `105` printed `Grade: A` because `105 >= 80` is true. I fixed this by adding an upfront input-validation check (`if (mark < 0 || mark > 100)`) that rejects out-of-range numbers before the grading ladder executes.

## 6. GitHub Workflow
- **Fork Repository URL:** https://github.com/hagreaves-odhiambo/kioto-ics2175-lab02
- **Working Branch Name:** student/ENB211-0061/2025/lab02
- **Pull Request URL:** https://github.com/Kiotolabs/kioto-ics2175-lab02/pull/1

<img width="1366" height="648" alt="Screenshot 2026-11-20 182617" src="https://github.com/user-attachments/assets/bf363e9d-3711-4b25-9ab2-562623f7e765" />

<img width="1364" height="713" alt="Screenshot 2026-11-20 182041" src="https://github.com/user-attachments/assets/a063aa40-98a2-4f4a-89d9-2326fbc532c4" />

## 7. Reflection
- **What I Learned:** I learned how condition ordering affects `else-if` ladders in C, why boundary values like `49` and `50` must be tested carefully, and how to use feature branches and pull requests to submit code cleanly.
- **What Was Difficult:** Ensuring the pull request pointed from my feature branch to `Kiotolabs/kioto-ics2175-lab02:main` rather than merging into my own fork's `main` branch required careful verification.
- **What I Will Do Differently Next Time:** I will write out my boundary test cases before coding so I include input validation from the very first draft.

## 8. Conclusion
All objectives of Laboratory 02 were successfully achieved. The C selection program compiled without warnings, accurately classified all standard, boundary, and invalid test inputs, and was properly published and submitted via a pull request to the official Kiotolabs repository.
