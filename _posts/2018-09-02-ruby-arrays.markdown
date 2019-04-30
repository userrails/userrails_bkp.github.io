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

Access value of nested array

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
```

Adding Data to nested Array

```
staffs_info[0] << "Rs. 80,000"
=> ["Ram", "0012", "Manager", "Rs. 80,000"]
staffs_info
=> [["Ram", "0012", "Manager", "Rs. 80,000"], ["Shyam", "0013", "HR Manager"], ["Hari", "0014", "Receptionist"]]
```

