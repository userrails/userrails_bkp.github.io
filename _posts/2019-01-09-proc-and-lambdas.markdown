---
layout: post
title:  "Lambdas and Proc"
date:   2019-01-07 08:01:18 +0545
categories: tutorials
---

Lambdas and Proc are block executing statement.

Lambdas and Proc both are object of Proc.

Lambdas and Proc are executed by call().

Lambda declaration

```
x = lambda { p "This is lambda" }
x.call
=> "This is lambda"

obj = lambda do |x, y|
  x+y
end
obj.call(2,3)
=> 5

# if required arguments are not supplied lambda throws argument errors
obj.call(2,3,5)
ArgumentError (wrong number of arguments (given 3, expected 2))
```

Proc declaration

```
x = Proc.new {p "this is proc"}
x.call
=> "this is proc"

obj = Proc.new do |x, y|
  x+y
end
obj.call(2,3)
=> 5

# if required arguments are not supplied it won't throw argument error like lambda
obj.call(2,3,5)
=> 5
```

```
class Block
  def hello(*args, &block)
    yield *args
  end

  proc = Proc.new do |*args|
    puts *args.class
    arr = *args
    sum = 0
    arr.flatten.each do |num|
      sum = sum + num
    end
    puts sum
  end

  obj = Block.new
  obj.hello([1,10,15], &proc)
end
=> Array
```
