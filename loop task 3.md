### TASK 3
```
rows = int(input("Enter the number of rows: "))
for i in range(rows):
    print(" " * (rows - i - 1), end="")
    print("*" * (2 * i + 1))
```
### OUTPUT
```
Enter the number of rows: 3
  *
 ***
*****
```
