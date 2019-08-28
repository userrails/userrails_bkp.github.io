### Inheritance in Ruby

Inheritance is the feature of OOP in which characteristics & behaviours of one class inherits into another class. The class which is inheriting behaviour is called subclass and class it inherits from is called superclass. Inheritance can also be used to remove duplication in your code and helps to achieve DRY "Don't Repeat Yourself" principle.


#### Class Inheritance

```
class Animal
    def eat # this method will overrides on other inherited classes
        puts "Animal eats grasses, water, etc"
    end
end

class Cat < Animal
end

class Cow < Animal
end
```

Here Animal is the superclass and Cat, Cow is the subclass.

```
cat = Cat.new
cow = Cow.new
cat.eat # => Animal eats grasses, water, etc
cow.eat # => Animal eats grasses, water, etc
```

#### Method overriding

```
class Animal
    def eat
        puts 'Animal eats grasses, water, etc'
    end
end

class Cat < Animal
    attr_accessor :food_name

    def initialize(food_name)
        @food_name = food_name
    end

    def eat
        puts "Cat eats #{food_name}"
    end
end

class Dog < Animal
end
```

```
cat = Cat.new("Milk and water")
cat.eat
# => Milk and water
dog = Dog.new
dog.eat
# => Animal eats grasses, water, etc
```

#### super

super is the inbuilt function of Ruby, which is used to call the methods up the inheritance hierarchy.

```
class Animal
  def eat
    "Animal"
  end
end

class Cat < Animal
  def eat
    super + " - cat - eats milk and water."
  end
end

cat = Cat.new
cat.eat        # => "Animal - cat - eats milk and water."
```
