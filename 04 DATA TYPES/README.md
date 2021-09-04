# Data type in Python
Như ở note về variable ta đã liệt kê được một số kiểu dữ liệu chính trong Python, ở note này ta sẽ đi sâu hơn về các đặc điểm của chúng 

## Các nhóm dữ liệu
+ Text type: str
+ Numeric types: int, float, complex
+ Sequence types: list, tuple, range
+ Mapping type: dict
+ Set type: set → value in set can not duplicate
+ Boolean: bool
+ None type: None (None is the data type of the class NoneType, its the same with null in other programming language, None isn't False, 0, empty string so any comparision with None will return False, except None itself. All variables refer to the same object when assign None, new instance of None is not created)

## Method to get type of variable
```python
var = 5
print(type(a)) # res = <class int>
```

## List
List là kiểu dữ liệu có thứ tự, mutable (changable). Một list có thể chứa nhiều variables có những kiểu dữ liệu khác nhau 

**Lưu ý:** 
+ Dưới đây là tóm tắt những thứ cơ bản về list mà mình thường dùng,  tham khảo đầy đủ hơn về list tại trang chủ của Python
+ Tìm hiểu thêm về list comprehension

```python
# multi-variables with different types
li = [3, [2, 5], 0.2]
```
### List unpacking
Ta có thêm một khái niệm khác với list là unpacking, xem ví dụ bên dưới
```python
colors = ['cyan', 'magenta', 'yellow', 'black']
cyan, magenta, other = colors # error, doesnt have enough variables to unpack
cyan, magenta, *other = colors # put * in front of variable

print(cyan) # cyan
print(magenta) # magenta
print(other) # ['yellow', 'black']
```
### Thêm phần tử vào list
Những cách dưới đây là mình thường dùng để thêm vào 1 list 
```python
# append ko unpack
a = [1, 2, 3]
a.append([4, 5, 6]) # res = [1, 2, 3, [4, 5, 6]]

# append unpack
# cách 1 - tốn bộ nhớ vì nó sẽ create new object 
a += [4, 5, 6] # res = [1, 2, 3, 4, 5, 6]

# cách 2 - thường dùng, ko create new object
a.extend([4, 5, 6]) # res = [1, 2, 3, 4, 5, 6]
```

### Tạo một list phần tử x với size n 
```python
li = [0] * n
li # res = [0 0...n]
```

### Indexing and Slicing
Index và slicing là kỹ thuật retrive phần tử từ một list, string hoặc tuple.  Indices có thể là một số dương (bắt đầu từ 0 và cũng có thể là một số âm  (bắt đầu từ -1 và  -1 là phần tử cuối cùng trong collection)

```python
# Indexing
a = [1, 2, 3]
a[1] # res = 2
a[-1] # res = 3

# Slicing
a = [1, 2, 3]
a[0:2] # res = [1, 2]

# Slicing and assignment
a = [1, 2, 3]
a[0:2] = [4, 5] # a = [4, 5, 3]

a = [1, 2, 3]
a[0:0] = [-3, -2, -1, 0] # a = [-3, -2, -1, 0, 1, 2, 3]

a = [-3, -2, -1, 0, 1, 2, 3]
a[2:4] = [] # a = [-3, -2, 1, 2, 3]
```

## String
Đọc thêm về list và string mình viết tại đây: [Link](https://github.com/nghoanglong/DataStructures-Algorithms-CheatSheet/tree/master/02%20DYNAMIC%20ARRAYS%20AND%20STRING)

## Tuples
Tuples là kiểu dữ liệu có thứ tự, immutable (unchangable)

**Lưu ý:** 
+ Dưới đây là tóm tắt những thứ cơ bản về tuple mà mình thường dùng,  tham khảo đầy đủ hơn về tuple tại trang chủ của Python
+ Indexing and slicing tuple giống với list
+ Unpack giống với list, tìm hiểu thêm về unpack trên google  

### Adding value to tuple
```python
tup = (3, 'hello')
tup += (2, 6)
tup # res = (3, 'hello', 2, 6)

# change value in tuple
tup[0] = 4 # res = error, ko thể change value in tuple
```

## Set
Set là kiểu dữ liệu unordered, unindexed và immutable. VÌ set unindexed nên ko thể sử dụng indexing và slicing, value trong set ko bị duplicated

**Lưu ý:** 
+ Dưới đây là tóm tắt những thứ cơ bản về set mà mình thường dùng,  tham khảo đầy đủ hơn về  set tại trang chủ của Python

### Retrive value in Set
```python
# Vì ko thể sử dụng indexing và slicing trong set, nên ta chỉ có thể dùng loop để lấy phần tử
a = {1, 4, 3, 1} # set ko có value duplicated nên a = {1, 4, 3, 1}
for value in a:
    print(value)
```

## Dictionaries
Dictionaries là kiểu dữ liệu unordered, mutable và indexed. Mọi value trong dictionary được lưu dưới dạng key-value

**Lưu ý:** 
+ Dưới đây là tóm tắt những thứ cơ bản về dictionary mà mình thường dùng,  tham khảo đầy đủ hơn về dictionary ại trang chủ của Python

### Retrive value in dictionary
```python
a = {'key': 'value', 'key2': 'value2'}
a['key'] # res = value
```
