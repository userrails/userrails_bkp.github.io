---
layout: post
title:  "Ruby - Loops & Iterators !"
date:   2018-09-01 04:19:12 +0545
categories: tutorials
---

Loop is the process in which set of instructions or block of codes are repeated in a specified number of times under certain condition is satisfied. for, while, do while are example of loops.

#### for loop
for loop is used to run block of code in a specific number of times when number of needed iterations is known.

```
for num in 1..100
  puts num
end 
```

Ruby each method is used to iterator over individual item in an array.

```
(1..100).each do |num|
  puts num
end

# loop through an array using each
[1, 2, 3].each do |i|
  puts i
end

# loop through hash using each
hash_var = {name: 'Car', color: 'Red', model: '2018'}
hash_var.each do |key, value|
  puts "#{key} => #{value}"
end

# find index in loop using each_with_index

[10, 11, 12].each_with_index do |val, key|
  p key
end
=> 0
   1
   2
```
