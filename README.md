## Bhavaharnath_AIE22162
## q-1
```
Function euclidean_distance(v1, v2):
    if length of v1 is not equal to length of v2:
        raise ValueError("Vectors should be of same dimension")
    sum_of_squares = 0
    for each element x, y in zip(v1, v2):
        sum_of_squares += (x - y) ** 2
    euclidean_distance = square_root(sum_of_squares)
    return euclidean_distance

Function manhattan_distance(v1, v2):
    if length of v1 is not equal to length of v2:
        raise ValueError("Vectors should be of same dimension")
    total_distance = 0
    for each element x, y in zip(v1, v2):
        total_distance += absolute_value(x - y)
    return total_distance

Function get_vector_from_input():
    prompt user to enter the vector (separated by commas)
    read the input as vector_str
    split the vector_str by comma and store it as a list of strings called vector_str_list
    initialize an empty list called vector
    for each string x in vector_str_list:
        convert x to float, strip whitespace, and append it to vector
    return vector

Print "Enter coordinates for vector 1:"
v1 = call get_vector_from_input()
Print "Enter coordinates for vector 2:"
v2 = call get_vector_from_input()

euclidean = call euclidean_distance(v1, v2)
manhattan = call manhattan_distance(v1, v2)

Print "Euclidean distance:" followed by euclidean
Print "Manhattan distance:" followed by Manhattan
```

## Explination
This Python code presents functions to calculate Euclidean and Manhattan distances between two vectors v1 and v2. It prompts  the user to input the coordinates of two vectors, calculates the distance and finally, the results are printed. The `get_vector_from_input()` function gets user input for vector coordinates The `euclidean_distance()` function calculates the Euclidean distance between two vectors, and the `manhattan_distance()` function computes the Manhattan distance. If the dimensions of the input vectors are not matched a `ValueError` is raised. 

## q-2

```
function euclidean_distance(v1, v2):
if len(v1) != len(v2):
return infinity  # Return a very large value to indicate incomparability
sum_of_squares = 0
for i in range(len(v1)):
sum_of_squares += (v1[i] - v2[i])^2
return sqrt(sum_of_squares)

function get_neighbors(training_data, test_instance):
distances = []
for train_data in training_data:
distance = euclidean_distance(train_data[0], test_instance)
distances.append((distance, train_data[1]))  # Appending distance and corresponding class label
distances.sort(key=lambda x: (x[0], x[1]))
return distances

function Knn_classifier(training_data, test_instance, k_value):
neighbors = get_neighbors(training_data, test_instance)
nearest_neighbors = neighbors[:k_value]  # Select k nearest neighbors
classes = [neighbor[1] for neighbor in nearest_neighbors]  # Extract class labels of nearest neighbors
class_counter = Counter(classes)
most_common_class = class_counter.most_common(1)[0][0]  # Get the most common class label among nearest neighbors
return most_common_class


training_data = [([140, 60], 'medium'), ([145, 55], 'medium'), ([165, 70], 'large'), ([170, 65], 'large'), ([155, 72], 'large')]
test_instance = [160, 58]
k_value = 2


result = Knn_classifier(training_data, test_instance, k_value)
print("Predicted class:", result)
```
## Explination
In the above python code , The `euclidean_distance` function computes the Euclidean distance between two vectors v1 and v2. The `get_neighbors` function calculates distances between the test instance and all training instances, sorts them by distance and class label and returns the sorted list. `Knn_classifier` function uses `get_neighbors` operation to select `k_value` closest neighbors.The KNN classifier predicts the class label of `test_instance` by looking at the majority class among `k_value` nearest neighbors in `training_data` which is then printed.

## q-3

```
FUNCTION label_encode_categorical(data):
    labels = {}             
    label_count = 0        
    encoded_data = []       

    FOR EACH value IN data:
        IF value NOT IN labels:
            labels[value] = label_count      
            label_count += 1                 
        encoded_data.append(labels[value])   

    RETURN encoded_data

# Example
categorical_data = ['India', 'Australia', 'England', 'India', 'England', 'Australia']
numeric_data = label_encode_categorical(categorical_data)

PRINT "Original categorical data:", categorical_data
PRINT "Numeric data after label encoding:", numeric_data
```
## Explination
In the above python code , The ` label_encode categorical` function iterates through each value in the input data. It assigns an unique numeric label to each unique categorical literal of the input, using an incremented counter. The function then returns a list where each list element is the assigned numeric label corresponding to the respective categorical value in the input data. It prints the original categorical data and also the corresponding numeric labels obtained by label encoding.

## q-4

```
function one_hot_encoding(data):
    unique_values = list(set(data))
    encoded_data = []
        for value in data:
        encoding = [0] * len(unique_values)
        index = unique_values.index(value)
        encoding[index] = 1
        encoded_data.append(encoding)
        return encoded_data
categorical_data = ['WI', 'IND', 'SL', 'WI', 'ENG', 'IND']
encoded_data = one_hot_encoding(categorical_data)
for i, encoded_value in enumerate(encoded_data):
    print(f'{categorical_data[i]}: {encoded_value}')
```


## Explination
In the above python code , It first identifies unique values in input data. After that, it runs through each value in the data and generates a one-hot encoded vector matching it where the index corresponding to the value's position in the unique values list is set to 1, and all other indices remain unchanged. These encodings are then appended to the list. It returns a list of encoded data in the form one-hot encoding of the corresponding input value.
