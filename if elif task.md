### if elif
```

number=int(input("Enter a number"))
if number > 0:
   print("number is positive")
elif number < 0:
   print("number is negative")
else:
  print("number is zero")
mark = int(input("Enter your mark (0-100): "))
if mark >= 100:
    print("Invalid")
elif mark >= 90:
    print("Grade A")
elif mark >= 80:
    print("Grade B")
elif mark >= 70:
    print("Grade C")
elif mark >= 60:
    print("Grade D")
else:
    print("Grade Fail")a=80
b=90
c=79
if b>a  and b>c:
 print("b is greater ")
username="admin"
password=1234
if password != 1234:
  print("invalid password")
if username != "admin":
  print("invalid user")
else:4
  print("Login successful!")
electricity_bill= int(input("enter a electricity_bill"))
if electricity_bill <100:
  print("low usage")
if electricity_bill <300
  print("medium usage")
if electricity_bill >300:
  print("high usage")
balance=10000
if 0 >= balance:
  print(" withdrawl sucessfully")
if 0 == balance:
  print("amount empty")
else:
  print("insufficent amount")
age = int(input("Enter the person's age: "))
if 0 <= age <= 12:
    print("Child")
elif 13 <= age <= 19:
    print("Teenager")
elif 20 <= age <= 59:
    print("Adult")
elif age >= 60:
    print("Senior Citizen")
else:
    print("Invalid age entered.")
```
### output
```
Enter a number54
number is positive
Enter your mark (0-100): 89
Grade B
b is greater 
Login successful!
enter a electricity_bill455
high usage
insufficent amount
Enter the person's age: 56
Adult


