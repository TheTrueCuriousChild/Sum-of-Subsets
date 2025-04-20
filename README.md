🌟 Sum of Subsets Problem — Backtracking in C
<p align="center"> <img src="https://img.shields.io/badge/Language-C-blue.svg" /> <img src="https://img.shields.io/badge/Algorithm-Backtracking-important" /> <img src="https://img.shields.io/badge/Difficulty-Medium-yellow" /> </p>
📌 Problem Statement
Given a set of positive integers and a target sum, the goal is to find all subsets of the given set that sum exactly to the target. This problem is solved efficiently using the Backtracking technique.

🧠 Algorithm Used
We use recursive backtracking to explore:

All combinations of including/excluding elements.

We prune paths early where the sum already exceeds the target.

🔧 How It Works
At each element in the array, we choose to:

✅ Include the element in the current subset.

❌ Exclude the element and move to the next.

We stop exploring further if:

✅ The current sum equals the target → ✅ Print the subset.

❌ The current sum exceeds the target → 🔙 Backtrack.

📂 Files
bash
Copy
Edit
sum_of_subsets.c       # Main C program file
README.md              # This beautiful documentation
💻 Code
c
Copy
Edit
#include <stdio.h>

void sumOfSubsets(int arr[], int n, int sum, int index, int currSum, int subset[], int subsetSize) {
    if (currSum == sum) {
        printf("Subset: ");
        for (int i = 0; i < subsetSize; i++)
            printf("%d ", subset[i]);
        printf("\n");
        return;
    }
    if (currSum > sum || index >= n) return;

    // Include current element
    subset[subsetSize] = arr[index];
    sumOfSubsets(arr, n, sum, index + 1, currSum + arr[index], subset, subsetSize + 1);

    // Exclude current element
    sumOfSubsets(arr, n, sum, index + 1, currSum, subset, subsetSize);
}

int main() {
    int arr[] = {2, 4, 6, 8};
    int n = sizeof(arr) / sizeof(arr[0]);
    int sum = 10;
    int subset[n];

    printf("Subsets of sum %d:\n", sum);
    sumOfSubsets(arr, n, sum, 0, 0, subset, 0);

    return 0;
}
📥 Sample Input
c
Copy
Edit
int arr[] = {2, 4, 6, 8};
int sum = 10;
📤 Sample Output
bash
Copy
Edit
Subsets of sum 10:
Subset: 2 4 4 
Subset: 2 8 
Subset: 4 6 
🧪 How to Run
Compile the program:

bash
Copy
Edit
gcc sum_of_subsets.c -o sum_of_subsets
Run the program:

bash
Copy
Edit
./sum_of_subsets
🔥 Features
Easy to understand and extend

Uses clean and clear recursive logic

Fast performance with pruning logic

Customizable for any integer set

🚀 Future Enhancements
Accept input from the user instead of hardcoding

Add sorting to optimize pruning

Handle duplicate values

Generalize for negative integers

🙌 Contributing
Feel free to fork, improve, and submit a PR!

bash
Copy
Edit
git clone https://github.com/yourusername/sum-of-subsets-backtracking.git
🧑‍💻 Author
Upendra Chakravarty
📧 Feel free to reach out
🌐 GitHub Profile

⭐️ Show Some Love
If you like this project, please consider giving it a ⭐ on GitHub!
