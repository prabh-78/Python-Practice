### set tasks
```
science_club = {"Aman", "Riya", "Karan", "Simran"}
sports_club = {"Karan", "Simran", "Rahul", "Neha"}
print("BEFORE ADDING",science_club)
print("BEFORE REMOVING",sports_club)
science_club.add("Rahul")
sports_club.remove("Rahul")
print("AFTER ADDING",science_club)
print("AFTER REMOVING",sports_club)
science_club.intersection(sports_club)
print("\n COMMON MEMBERS",science_club.intersection(sports_club))
science_club.union(sports_club)
print("\n ALL MEMBERS:",science_club.union(sports_club))
print("\n MEMBERS ONLY IN SCIENCE CLUB:", science_club.difference(sports_club))
print("\n IS AMAN IN SCIENCE CLUB:", "Aman" in science_club)
temp_set={"test1","test2","test3"}
print("TEMPORARY SET:",temp_set)
print("AFTER CLEARING:",temp_set.clear())
```
### output
```
BEFORE ADDING {'Simran', 'Karan', 'Aman', 'Riya'}
BEFORE REMOVING {'Simran', 'Rahul', 'Karan', 'Neha'}
AFTER ADDING {'Simran', 'Karan', 'Riya', 'Rahul', 'Aman'}
AFTER REMOVING {'Simran', 'Karan', 'Neha'}

 COMMON MEMBERS {'Simran', 'Karan'}

 ALL MEMBERS: {'Simran', 'Rahul', 'Karan', 'Aman', 'Neha', 'Riya'}

 MEMBERS ONLY IN SCIENCE CLUB: {'Rahul', 'Aman', 'Riya'}

 IS AMAN IN SCIENCE CLUB: True
TEMPORARY SET: {'test1', 'test3', 'test2'}
AFTER CLEARING: None
```
