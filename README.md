# Ex.No.6 AI-Assisted Programming and Debugging

# Date:26.11.26
# Register no:212225040470
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

#AI Tools Required:

# Explanation:
Experiment the persona pattern as a programmer for any specific applications related with your interesting area. 
Generate the outoput using more than one AI tool and based on the code generation analyse and discussing that. 
Learnerss generate

Python
C
Java
using AI.

Then

identify bugs
optimise code
explain complexity
generate unit tests
Finally compare manual coding versus AI-assisted coding. 
Deliverable


### 1. Persona-Based Prompt

**Prompt:**

"You are an experienced software programmer. Develop a Student Performance Analysis System that accepts marks for five subjects, calculates the average mark, and determines the student's grade. Generate the solution in Python, C, and Java. Ensure the program handles invalid marks, uses readable code, and follows good programming practices. Identify possible bugs, optimize the solution, explain time and space complexity, and generate unit test cases."

### 2. Expected Application Functionality

- Accept marks for five subjects.
- Validate that each mark is between 0 and 100.
- Calculate the total and average.
- Assign a grade based on the average.
- Display the student's performance.

### 3. Python Implementation

```python
def calculate_average(marks):
    if len(marks) != 5:
        raise ValueError("Enter marks for exactly five subjects")

    if any(mark < 0 or mark > 100 for mark in marks):
        raise ValueError("Marks must be between 0 and 100")

    return sum(marks) / len(marks)


def calculate_grade(average):
    if average >= 90:
        return "A"
    elif average >= 80:
        return "B"
    elif average >= 70:
        return "C"
    elif average >= 50:
        return "D"
    else:
        return "F"


marks = [85, 90, 78, 88, 92]

average = calculate_average(marks)
grade = calculate_grade(average)

print("Total:", sum(marks))
print("Average:", average)
print("Grade:", grade)
```

**Sample Output:**

```text
Total: 433
Average: 86.6
Grade: B
```

### 4. C Implementation

```c
#include <stdio.h>

int main() {
    int marks[5];
    int total = 0;
    float average;

    printf("Enter marks for five subjects:\n");

    for (int i = 0; i < 5; i++) {
        scanf("%d", &marks[i]);

        if (marks[i] < 0 || marks[i] > 100) {
            printf("Invalid mark entered.\n");
            return 1;
        }

        total += marks[i];
    }

    average = total / 5.0;

    printf("Total: %d\n", total);
    printf("Average: %.2f\n", average);

    if (average >= 90)
        printf("Grade: A\n");
    else if (average >= 80)
        printf("Grade: B\n");
    else if (average >= 70)
        printf("Grade: C\n");
    else if (average >= 50)
        printf("Grade: D\n");
    else
        printf("Grade: F\n");

    return 0;
}
```

**Sample Output:**

```text
Enter marks for five subjects:
85
90
78
88
92
Total: 433
Average: 86.60
Grade: B
```

### 5. Java Implementation

```java
public class StudentPerformance {

    public static double calculateAverage(int[] marks) {
        if (marks.length != 5) {
            throw new IllegalArgumentException(
                "Enter marks for exactly five subjects"
            );
        }

        int total = 0;

        for (int mark : marks) {
            if (mark < 0 || mark > 100) {
                throw new IllegalArgumentException(
                    "Marks must be between 0 and 100"
                );
            }

            total += mark;
        }

        return total / 5.0;
    }

    public static String calculateGrade(double average) {
        if (average >= 90) return "A";
        else if (average >= 80) return "B";
        else if (average >= 70) return "C";
        else if (average >= 50) return "D";
        else return "F";
    }

    public static void main(String[] args) {
        int[] marks = {85, 90, 78, 88, 92};

        double average = calculateAverage(marks);
        int total = 0;

        for (int mark : marks) {
            total += mark;
        }

        System.out.println("Total: " + total);
        System.out.println("Average: " + average);
        System.out.println("Grade: " + calculateGrade(average));
    }
}
```

**Sample Output:**

```text
Total: 433
Average: 86.6
Grade: B
```

## 6. Multiple AI Tools – Output Comparison

The same persona-based prompt can be submitted to ChatGPT, Gemini, and Claude.

| AI Tool | Expected Contribution |
|---|---|
| ChatGPT | Generates code and explains the program structure. |
| Google Gemini | Suggests alternative implementations and improvements. |
| Claude | Reviews readability, validation, and possible edge cases. |

**Analysis:** All three tools can assist with generating the same application. Their actual outputs may differ in code structure, explanation, and error handling. The generated programs should be executed and tested before accepting them.

*Note: The descriptions above are an illustrative comparison, not verified live outputs from the three AI tools.*

## 7. Bug Identification and Debugging

Some possible bugs in the Student Performance Analysis System are:

| Bug | Description | Solution |
|---|---|---|
| Invalid marks | Marks greater than 100 or less than 0 are accepted. | Add input validation. |
| Incorrect average | Integer division may produce an inaccurate average. | Use floating-point division. |
| Incorrect subject count | The program may calculate an average using the wrong number of subjects. | Check that exactly five marks are entered. |
| Incorrect grade | Grade conditions may be checked in the wrong order. | Check higher grade boundaries first. |

### Example of a Buggy Python Statement

```python
average = total // 5
```

**Problem:** The `//` operator performs integer division and removes the decimal portion.

**Corrected Statement:**

```python
average = total / 5
```

**Improvement:** The corrected statement preserves decimal values and produces a more accurate average.

## 8. Code Optimization

The program can be improved by:

1. Using functions to avoid repeated code.
2. Validating inputs before processing.
3. Using meaningful variable names.
4. Separating average calculation from grade calculation.
5. Using loops instead of repeating statements.
6. Handling invalid inputs properly.

## 9. Time and Space Complexity

Let `n` represent the number of subjects.

| Operation | Time Complexity |
|---|---|
| Validate marks | O(n) |
| Calculate total | O(n) |
| Calculate average | O(1) |
| Determine grade | O(1) |
| Overall program | O(n) |

**Space Complexity:** O(n), because the program stores the marks in an array or list.

For the five-subject example, the input size is fixed, so the program performs a small, predictable amount of work.

## 10. Unit Test Cases

| Test Case | Input Marks | Expected Result |
|---|---|---|
| Test 1 | 85, 90, 78, 88, 92 | Average = 86.6, Grade = B |
| Test 2 | 95, 96, 98, 94, 97 | Grade = A |
| Test 3 | 70, 75, 72, 78, 71 | Grade = C |
| Test 4 | 40, 45, 48, 42, 45 | Grade = F |
| Test 5 | 85, 90, 110, 88, 92 | Invalid marks |
| Test 6 | Only four marks | Invalid subject count |

### Python Unit Testing

```python
import unittest

class TestStudentPerformance(unittest.TestCase):

    def test_average(self):
        marks = [85, 90, 78, 88, 92]
        self.assertAlmostEqual(
            calculate_average(marks), 86.6
        )

    def test_grade(self):
        self.assertEqual(calculate_grade(95), "A")
        self.assertEqual(calculate_grade(85), "B")
        self.assertEqual(calculate_grade(75), "C")
        self.assertEqual(calculate_grade(55), "D")
        self.assertEqual(calculate_grade(40), "F")

    def test_invalid_marks(self):
        with self.assertRaises(ValueError):
            calculate_average([85, 90, 110, 88, 92])

    def test_invalid_subject_count(self):
        with self.assertRaises(ValueError):
            calculate_average([85, 90, 78, 88])


if __name__ == "__main__":
    unittest.main()
```

## 11. Manual Coding vs AI-Assisted Coding

| Manual Coding | AI-Assisted Coding |
|---|---|
| Code is written completely by the programmer. | AI helps generate code from prompts. |
| Debugging is performed manually. | AI can suggest possible bugs and fixes. |
| Requires independent knowledge of syntax. | Provides syntax suggestions and explanations. |
| Code optimization is performed manually. | AI can recommend optimization techniques. |
| Unit tests must be written manually. | AI can generate test cases. |
| Gives the programmer direct control over every implementation decision. | Requires human review to verify generated code. |

### Analysis

Manual coding helps programmers develop problem-solving and programming skills. AI-assisted coding can reduce development time and provide useful suggestions. However, AI-generated code may contain errors, so programmers must test and verify the results.

## 12. Actionable Insights

- Use AI tools to understand unfamiliar programming concepts.
- Compare outputs from multiple AI tools before choosing an implementation.
- Validate all AI-generated code by compiling and executing it.
- Use unit testing to identify errors.
- Check time and space complexity before accepting an optimization.
- Never depend completely on AI-generated code without understanding it.

## Conclusion

AI-assisted programming helps developers generate code, identify bugs, optimize programs, explain complexity, and create unit tests. Comparing multiple AI tools provides different approaches to solving the same programming problem. Manual coding remains important for developing programming knowledge, while AI assistance improves productivity when used responsibly.


# Result: The corresponding Prompt is executed successfully.
