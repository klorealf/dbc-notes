# General Ruby 

## CLASSES
### Initialize recieving a hash argument
```ruby
class ClassName
  def initialize(args)
    @name = args[:name] || "Default Name"
    @married = args.fetch(:married, false)
  end
end
#args[:key] - set nil by default if no matching key is found and no default is given  
#args.fetch(:key) - gives an error if no matching key is found and no default is given  
```
### Class Constants
```ruby
class ClassName
  CLASS_CONSTANT = "Is convention to name it in caps ^^"
end
# To access the constant from outside the class:
ClassName::CLASS_CONSTANT
```
### Inheritance
```ruby
class Class < SuperClass
  def initialize
   super                        #Copies all that is inside initialize from SuperClass
   @classvar = "Another Value"  #You can still add things after that
  end 
end
```
### Printing name from Class
When you try to print an instance from a class you will get the reference of the object, like: `#<Cat:0x007fc4a1969688>`. Ruby is printing the default `to_s` method set for classes, and the default is to print the name of the object and it's reference. You can create a custom `to_s` method to you class so it will print whatever you want! 
```ruby
class Cat
  attr_reader :name
  def initialize
    @name = "Whiskers"
  end 
  
  def to_s
    "#{name}, the cat!"
  end
  
end

cat1 = Cat.new
puts "#{cat1}" # => `Whiskers, the cat!`
```
The last `puts` will print `Whiskers, the cat!` instead of the standart `#<Cat:0x007fc4a1969688>`
### Comments
`@@`- Class Variable  
`@`- Instance Variable  

## GENERAL RUBY
### Recursion
```ruby
def countdown(n)
  return if n.zero? # base case
  puts n
  countdown(n-1)    # getting closer to base case
end

countdown(5) # => 5,4,3,2,1
```
### Reduce
```ruby 
  #collection.reduce(initial_value, :name_of_method)
  [2,2,3].reduce(0, :+) => 7
  [2,2,3].reduce(1, :*) => 12
  #Also take blocks
  [2,2,3].reduce(1) {|sum,element| sum*element}
```

## GitHub Markdown Resources
- [Highlight Code Blocks](https://help.github.com/articles/creating-and-highlighting-code-blocks/)
- [Writing on GitHub](https://help.github.com/categories/writing-on-github/)
