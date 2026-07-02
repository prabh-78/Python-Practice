### set tasks
```
set1={1,2,3,4}
set2={3,4,5,6}
print(set1)
print(set2)
print("------/result/-------")
set1.union(set2)
print("union",set1.union(set2))
set1.intersection(set2)
print("intersection",set1.intersection(set2))
set2.difference(set1)
print( "difference",set2.difference(set1))
set1.symmetric_difference(set2)
print("symmetric difference",set1.symmetric_difference(set2))

```
### output
```
{1, 2, 3, 4}
{3, 4, 5, 6}
------/result/-------
union {1, 2, 3, 4, 5, 6}
intersection {3, 4}
difference {5, 6}
symmetric difference {1, 2, 5, 6}
```
