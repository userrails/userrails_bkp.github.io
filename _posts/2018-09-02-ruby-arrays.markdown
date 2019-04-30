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

