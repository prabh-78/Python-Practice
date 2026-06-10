## python string functions practice task
```
full_name=input("enter your full name:")
course_name=input("enter your course name:")
city=input("enter your city:")
print("student {} is enrolled in {} and lives in {}".format(full_name, course_name, city))
print(full_name.center(40, "*"))
print(course_name.split())
N=["learn","code","grow"]
print("|".join(N))
print("first character:",full_name[0])
print("last character:",full_name[-1])
print("middle part:",full_name[1:11])
print("first 5 charcter:",full_name[0:5])

```
## output 
```
enter your full name:rahul sharma
enter your course name:python programming
enter your city:ludhaina
student rahul sharma is enrolled in python programming and lives in ludhaina
**************rahul sharma**************
['python', 'programming']
learn|code|grow
first character: r
last character: a
middle part: ahul sharm
first 5 charcter: rahul
```

