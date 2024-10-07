
## *7. Practice Tasks*

7.1 Write a C++ program to create two pointers of integer type, now take values in these
pointers and pass them to a function. Function will update both the values by adding “1” to them.
Display the updated values in main.
---
```
#include <iostream>
using namespace std;


void updateValues(int* ptr1, int* ptr2) {
    (*ptr1)++;
    (*ptr2)++;
}

int main() {
    cout << "Name: Muhammad Usman \nReg No: BCS233134 \n"<< endl;
    int num1, num2;
    int *ptr1, *ptr2;

    cout << "Enter value for a: ";
    cin >> num1;
    cout << "Enter value for b: ";
    cin >> num2;

    ptr1 = &num1;
    ptr2 = &num2;

    updateValues(ptr1, ptr2);

    cout << "Updated value of a: " << num1 << endl;
    cout << "Updated value of b: " << num2 << endl;

    return 0;
}
```


7.2 Create a dynamic array of user defined size. Now take input in array from user. Take a
new (integer) value from user and search that how many times the entered number is present in
the array.
---
```
#include <iostream>
using namespace std;

int main() {
    cout << "Name: Muhammad Usman \nReg No: BCS233134 \n"<< endl;
    int size, searchValue, count = 0;
    cout << "Enter the size: ";
    cin >> size;

    int* arr = new int[size];

    cout << "Enter " << size << " numbers: ";
    for (int i = 0; i < size; i++) {
        cin >> arr[i];
    }

    cout << "Enter the value to search for: ";
    cin >> searchValue;

    for (int i = 0; i < size; i++) {
        if (arr[i] == searchValue) {
            count++;
        }
    }

    cout << "The value " << searchValue << " is present " << count << " times in the array." << endl;

    delete[] arr;

    return 0;
}
 ```


7.3 Write a program to create a dynamic array of user defined size. Array should be of
character type. Write a function ChangeCase() that should convert all the small alphabets to
capital and vice versa. All array operations should be done using pointers.
---
```
#include <iostream>
using namespace std;
// Function to change the case of characters
void ChangeCase(char* arr, int size) {
    for (int i = 0; i < size; i++) {
        if (arr[i] >= 'a' && arr[i] <= 'z') {
            arr[i] = arr[i] - 'a' + 'A'; // uppercase
        } else if (arr[i] >= 'A' && arr[i] <= 'Z') {
            arr[i] = arr[i] - 'A' + 'a'; // lowercase
        }
    }
}

int main() {
    cout << "Name: Muhammad Usman \nReg No: BCS233134 \n"<< endl;
    int size;
    cout << "Enter the size: ";
    cin >> size;

    char* arr = new char[size];
    cout << "Enter " << size << " characters: ";
    for (int i = 0; i < size; i++) {
        cin >> arr[i];
    }

    ChangeCase(arr, size);
   
    cout << "New array: ";
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    
    cout << endl;
    
    delete[] arr;

    return 0;
}

 ```

7.4 Write a program to create a dynamic array of user defined size. Size should be in the
range of 0 to 15. Write a function FindLarge that should ask user to enter a non-negative number.
Function should find the next largest number than the input number in the list.<br>
Sample input:<br>
Enter size: 5<br>
After insertion:<br>
13 4 55 29 32<br>
Sample output:<br>
Enter number: 15<br>
Next largest number from 15 is: 29<br>
----
 ```
#include <iostream>
using namespace std;

// Function to find the largest number in the array
int FindLarge(int* arr, int size, int num) {
    int nextL = -1;

    for (int i = 0; i < size; i++) {
        if (arr[i] > num) {
            if (nextL == -1 || arr[i] < nextL) {
                nextL = arr[i];
            }
        }
    }
    return nextL;
}

int main() {
    cout << "Name: Muhammad Usman \nReg No: BCS233134 \n"<< endl;
    int size;
    do {
        cout << "Enter the size (0 to 15): ";
        cin >> size;
    } while (size < 0 || size > 15);

    int* arr = new int[size];

    cout << "Enter " << size << " Numbers: ";
    for (int i = 0; i < size; i++) {
        cin >> arr[i];
    }

    int num;
    cout << "Enter a number to search : ";
    cin >> num;

    int res = FindLarge(arr, size, num);

    if (res != -1) {
        cout << "Next largest number from " << num << " is: " << res << endl;
    } else {
        cout << "There is no number larger than " << num << " in the array." << endl;
    }

    delete[] arr;

    return 0;
}
```

 

