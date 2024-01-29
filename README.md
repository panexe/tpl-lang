# tpl-lang
The language of the future, the present and the past.

TPL is a temporal DSL to help timetravelers to estimate the consequences of their actions. It enables you to modify values in the past, present or future. Every program guarantees is guaranteed to fully resolve to a deterministic state.

## examples

Hello world:
```tpl
set value = 0
time ƛ
if value > 0
    print "world"
else
    print "hello "
    set value = 1 at ƛ
resolve
```


Endless loop printing hello
```tpl
set value = 0
time ƛ
if value > 0
    print "world"
else
    print "hello "
    set value = 0 at ƛ
resolve
```

### Instructions

`resolve` travels to the earliest point that has had changes that were not yet encountered. Continue if there are no unaccounted changes. All names are reset to the values they had when we last were at POINT.

`destroy POINT` destroys the current timeline and travels to point POINT. All names are reset to the values they had when we last were at POINT.

`EXPRESSION` an expression can be a number, a name, or something like `EXPRESSION OPERATOR EXPRESSION`

`set NAME = EXPRESSION` sets a name to the value of a expression.

`set NAME = EXPRESSION at POINT` the next time we are at POINT, name is set to EXPRESSION. expression is evaluated now.

`suicide` terminates the program.

`if EXPRESSION OPERATOR EXPRESSION` is a normal if statement


### Program structure

Every valid program needs to end with resolve or suicide.








