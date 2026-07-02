### tuple
```

animals = ["lion", "tiger", "bear", "wolf"]
colors = ["red", "blue", "green", "yellow"]
for animal in animals:
    print(animal)
    i = 0
while i < len(colors):
    print(colors[i])
    i += 1
animals_tuple = tuple(animals)
colors_tuple = tuple(colors)
combined_animals_colors_tuple = animals_tuple + colors_tuple
print(f"Combined Animals and Colors Tuple: {combined_animals_colors_tuple}")
repeated_tuple = animals_tuple * 2
print(f"Original animals_tuple: {animals_tuple}")
print(f"Repeated animals_tuple: {repeated_tuple}")
repeated_tuple = colors_tuple * 3
print(f"Original colors_tuple: {colors_tuple}")
print(f"Repeated colors_tuple: {repeated_tuple}")
```
### output
```
lion
tiger
bear
wolf
red
blue
green
yellow
Animals as tuple: ('lion', 'tiger', 'bear', 'wolf')
Colors as tuple: ('red', 'blue', 'green', 'yellow')
Combined Animals and Colors Tuple: ('lion', 'tiger', 'bear', 'wolf', 'red', 'blue', 'green', 'yellow')
Original animals_tuple: ('lion', 'tiger', 'bear', 'wolf')
Repeated animals_tuple: ('lion', 'tiger', 'bear', 'wolf', 'lion', 'tiger', 'bear', 'wolf')
Original colors_tuple: ('red', 'blue', 'green', 'yellow')
Repeated colors_tuple: ('red', 'blue', 'green', 'yellow', 'red', 'blue', 'green', 'yellow', 'red', 'blue', 'green', 'yellow')

