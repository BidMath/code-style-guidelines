# Ruby

## Guidelines

### Indentation

Always 2 spaces.

### Braces in methods

We **should not** use [*seattle.rb style*](https://twitter.com/mrb_bk/status/429000440429031424):

```ruby
method a
```

**Our way**:

```ruby
method(a)
```


---

### block delimiters

( in docs of File class)
```ruby
# read the counter using read lock
File.open("counter", "r") {|f|
  f.flock(File::LOCK_SH)
  p f.read
}
```

**Our way**:

```ruby
File.open(f) do |f|
  f.flock(File::LOCK_SH)
  p f.read  
end
```

---

Other ways:

```ruby
let(:bla) {
  %|
    Select things from
    other_big_thing
  |
}
```

**Our way**:

```ruby
let(:bla) do
  %|
    Select things from
    other_big_thing
  |
end
```

---

### Multi line strings:

Other ways:

```ruby
let(:bla) {
  %|
    Select things from
    other_big_thing
  |
}
```

**Our way**:

```ruby
let(:bla) do
  %|
    Select things from
    other_big_thing
  |
end
```

### Multi line Operations

```ruby
very_very_big_obj_name.method1()
                      .method2()
                      .method3()
                      .method4()
```

**Our way**:

```ruby
very_very_big_obj_name
  .method1()
  .method2()
  .method3()
  .method4()
```


### Quotes

Other ways:
 
```ruby
STR_VARIABLE='str variable'
```

**Our way**:
 
```ruby
STR_VARIABLE="str variable"
```

Always use "", except when you need to use " as a 

```ruby
EDGE_CASE_ONE="\"edge\" case one"
```

**Our way**:
 
```ruby
EDGE_CASE_ONE='"edge" case one'
```

### Multi args
```ruby
method(
  "1","1","1","1","1","1","1","1","1")
```

**Our way**:

```ruby
method(
  "1","1","1","1","1","1","1","1","1"
)
```


### Backslash

Avoid use \, prefer rewrite code in other ways.

### Multi line strings

Other way:
```ruby
string =
  "Select things from" \
  "other_big_thing"
```

**Our way 1**:

```ruby
string =
  %|
    Select things from
    other_big_thing
  |
```

**Our way 2**:

```ruby
string =
  "Select things from" +
  "other_big_thing"
```

### Array of Words and Symbols
We don't enforce `%w` or `%i`

**Our way 1**:
```ruby
STATES = ['draft', 'open', 'closed']
STATES = [:draft, :open, :closed]
```

**Our way 2**:
```ruby
STATES = %w(draft open closed)
STATES = %i(draft open closed)
```
