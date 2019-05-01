---
layout: post
title:  "Ruby - Arrays !"
date:   2018-09-02 09:01:18 +0545
categories: tutorials
---

An array is an ordered collection of elements that can be of any type. Each element in an array is referred to by an index. Array can have objects like integer, string, float, Fixnum, Hash, Symbol.

Creating / Initialization of an Array

```
arr = Array.new
```

Set array size

```
arr = Array.new(50)
puts arr.size # 50
puts arr.length # 50
```

Assign a value of an array

```
arr1 = Array.new([1,2,3,4,5])
arr2 = [1,2,3,4,5]
```

Accessing elementes

```
arr1[3] => 4
arr1[50] => nil
arr1[-3] => 3
arr1[0, 4] => [1,2,3,4] # 0 is the indexing value and 4 is 4 items including indexing value 0
arr1[1..3] => [2,3,4]
arr1.at(1) => 2
arr1.fetch(4) => 5
arr1.first => 1
arr1.last => 5
arr1.take(3)
=> [1, 2, 3]
arr1.drop(3)
=> [4, 5]

arr = [1,2,3,4,5]
arr.count => 5
arr.empty? # => false
arr.include?(2) => true
```

Check if two array objects are equal

```
# checks the value
arr1.eql? arr2
=> true

# checks the references of the object, object id
arr1.equal? arr2
=> false
# This is because object_id for both object is different
arr1.object_id = 11544620
arr2.object_id = 11617600

arr1 = arr2
arr1.equal? arr2 
=> true
# Now object_id for both object is same
arr1.object_id = 11617600
arr2.object_id = 11617600
```

Word array create an array in which each entry is a single word.

'''
count  = %w{one two three four five}
'''

This is equivalent to

```
count = ["one", "two", "three", "four", "five"]
```

Nested Array: Array can contains other arrays

```
staffs_info = [
  ["Ram", "0012", "Manager"],
  ["Shyam", "0013", "HR Manager"],
  ["Hari", "0014", "Receptionist"]
]
```

Accessing value of nested array

```
staffs_info[0][1]
=> "0012"
```

Adding Data to Array

```
count << "six"
 => ["one", "two", "three", "four", "five", "six"]

count.push("seven")
=> ["one", "two", "three", "four", "five", "six", "seven"]

# insert first position of an array
count.unshift("zero")
=> ["zero", "one", "two", "three", "four", "five"]

# insert at any position
count.insert(5, "between 4 & 5")
=> ["zero", "one", "two", "three", "four", "between 4 & 5", "five"]

# insert multivalues once
count.insert(3, 'bet 2-3 1', 'bet2-3 2', 'bet2-3 3')
=> ["zero", "one", "two", "bet 2-3 1", "bet2-3 2", "bet2-3 3", "three", "four", "between 4 & 5", "five"]
```

Adding Data to nested Array

```
staffs_info[0] << "Rs. 80,000"
=> ["Ram", "0012", "Manager", "Rs. 80,000"]
staffs_info
=> [["Ram", "0012", "Manager", "Rs. 80,000"], ["Shyam", "0013", "HR Manager"], ["Hari", "0014", "Receptionist"]]
```

Array pop / Remove items from an array

```
arr = [1,2,3,4,5]
arr.pop
=> 5
arr
=> [1,2,3,4]

# array.unshift(0) will add o to start of an array while array.shift will remove first element
arr = [1,2,3,4,5]
arr.shift 
=> 1
arr
[2,3,4,5]

# delete an item at particular index use delete_at(index_position)
arr = [1,2,3,4,5]
arr.delete_at(2)
=> 3
arr
[1,2,4,5]

# compact() is used to remove nil value from an array
arr = [nil, 1, 2, 3, nil, 4, nil, 5]
arr.compact
[1,2,3,4,5]
arr
=> [nil, 1, 2, 3, nil, 4, nil, 5]
arr.compact!
=> [1,2,3,4,5]
arr
=> [1,2,3,4,5]

arr = [1,1,2,2,3,3,4,4,5,6,7]
arr.uniq
=> [1, 2, 3, 4, 5, 6, 7]
```

Iterating over an Array

```
arr = [1,2,3,4,5]
arr.each {|item| p item+10}
=> it prints 11,12,13,14,15

arr = [1,2,3,4,5]
arr.reverse_each {|item| p item+10}
=> it prints 15,14,13,12,11

arr = [1,2,3,4,5]
arr.map {|item| p item+10}
=> it prints 11,12,13,14,15
arr
=> 1,2,3,4,5

arr.map! {|item| p item+10}
arr
=> [11, 12, 13, 14, 15]

```

Selecting items from an Array

Non-destructive Selection

```
arr = [1,2,3,4,5,6,7,8]
arr.select {|a| a > 3}
# => [4,5,6,7,8]
arr.reject {|a| a < 3}
# => [3,4,5,6,7,8]
arr.drop_while {|a| a < 5}
# => [5,6,7,8]
arr
=> [1,2,3,4,5,6,7,8] 
```

Destructive Selection

Destructive methods are select! and reject!

```
arr.select! {|a| a > 3}
=> [4, 5, 6, 7, 8]
arr
=> [4, 5, 6, 7, 8]


> arr = [1,2,3,4,5,6,7,8]
=> [1, 2, 3, 4, 5, 6, 7, 8] 
> arr.delete_if { |a| a < 4 }
=> [4, 5, 6, 7, 8] 
> arr
=> [4, 5, 6, 7, 8]

arr = [1, 2, 3, 4, 5, 6, 7, 8]
arr.keep_if { |a| a < 4 }
[1,2,3]
arr
=> [1, 2, 3]
```

Public methods like &, |, &&, ||

```
a = [1, 2, 3, 4]
b = [3, 4, 5, 6]

a & b
=> [3, 4]

a | b
=> [1, 2, 3, 4, 5, 6]

a || b
=> [1, 2, 3, 4]

a && b
=> [3, 4, 5, 6]

```