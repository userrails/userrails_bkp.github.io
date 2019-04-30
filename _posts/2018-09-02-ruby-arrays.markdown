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