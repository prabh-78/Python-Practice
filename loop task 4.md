### TASK 4
```
rows = int(input("Enter the number of rows: "))
for i in range(rows):
    print(" " * i , end="")
    print("*" * (2 * (rows - i ) - 1))
```
### OUTPUT
```
Enter the number of rows: 5
*********
 *******
  *****
   ***
    *
```
