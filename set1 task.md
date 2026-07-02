### set
```
set1={1,2,3,4}
set2={3,4,5,6}
set1.union(set2)
print(set1.union(set2))
set1.intersection(set2)
print(set1.intersection(set2))
set1.difference(set2)
print(set1.difference(set2))
set2.difference(set1)
print(set2.difference(set1))
set1.symmetric_difference(set2)
print(set1.symmetric_difference(set2))

```
### output
```
{1, 2, 3, 4, 5, 6}
{3, 4}
{1, 2}
{5, 6}
{1, 2, 5, 6}
```
