---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.16.2
---

# Looping and Control Statements

This notebook introduces looping and control statements in Python, focusing on how these concepts can be applied in geospatial programming. Understanding loops and control flow is essential for processing and analyzing geographic data efficiently.

+++

## For Loops

For loops allow you to iterate over a sequence (such as a list, tuple, or string) and execute a block of code for each item in the sequence. This is particularly useful in geospatial programming when you need to process multiple features or coordinates.

```{code-cell}
coordinates = [
    (35.6895, 139.6917),
    (34.0522, -118.2437),
    (51.5074, -0.1278),
]  # List of tuples representing coordinates

for lat, lon in coordinates:
    print(f"Latitude: {lat}, Longitude: {lon}")
```

## While Loops

While loops continue to execute a block of code as long as a specified condition is true. They are useful when the number of iterations is not known beforehand, such as when processing data until a certain condition is met.

```{code-cell}
counter = 0
while counter < len(coordinates):
    lat, lon = coordinates[counter]
    print(f"Processing coordinate: ({lat}, {lon})")
    counter += 1
```

## Control Statements: if, elif, else

Control statements allow you to execute different blocks of code based on certain conditions. In geospatial programming, this is useful for handling different types of data or conditions.

```{code-cell}
for lat, lon in coordinates:
    if lat > 40:
        print(f"{lat} is in the Northern Hemisphere")
    elif lat < -40:
        print(f"{lat} is in the Southern Hemisphere")
    else:
        print(f"{lat} is near the equator")
```

## Combining Loops and Control Statements

You can combine loops and control statements to perform more complex operations, such as filtering data or applying conditions during iteration.

```{code-cell}
filtered_coordinates = []
for lat, lon in coordinates:
    if lon > 0:
        filtered_coordinates.append((lat, lon))
print(f"Filtered coordinates (only with positive longitude): {filtered_coordinates}")
```

## Exercises

1. Create a list of cities with their coordinates. Write a for loop to print out only the cities that are in the Northern Hemisphere.
2. Write a while loop that continues to print the coordinates in a list until a coordinate with a latitude less than 0 is found.
3. Create a for loop that iterates through a list of coordinates and prints whether each coordinate is in the Eastern or Western Hemisphere based on the longitude.
4. Combine a for loop and if statements to count how many coordinates in a list are located in the Southern Hemisphere.

```{code-cell}
# Type your code here
```

## Conclusion

Loops and control statements are fundamental tools in geospatial programming. They allow you to process and analyze geographic data efficiently by automating repetitive tasks and applying logic based on data conditions. Practice these concepts by applying them to your geospatial datasets and analyses.
