# Variables, Booleans and None

## Variables

Variables are easy to understand. They simply **contain data**. Actually
they [point to data](https://www.youtube.com/watch?v=_AEJHKGk9ns), but
think about them as data containers for now.

```py
>>> a = 1      # create a variable called a and assign 1 to it
>>> a          # get the value of a and let Python echo it
1
>>>
```

We can also change the value of a variable after setting it.

```py
>>> a = 2
>>> a
2
>>> 
```

Trying to access a variable that is not defined is an error.

```py
>>> thingy
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'thingy' is not defined
>>> 
```

Variables are an important part of most programming languages, and they
allow programmers to write much larger programs than they could write
without variables.

Variable names can be multiple characters long. They can contain
uppercase characters, numbers and some other characters, but most of
the time you should use simple, lowercase variable names. You can also
use underscores.

```py
>>> number_one = 1
>>> number_two = 2
>>> 
```

Python also has some words that cannot be used as variable names
because they have a special meaning. They are called **keywords**, and
you can run `help('keywords')` to see the full list if you want to.
We'll learn to use most of them later in this tutorial. Trying to use a
keyword as a variable name causes a syntax error.

```py
>>> if = 123
  File "<stdin>", line 1
    if = 123
       ^
SyntaxError: invalid syntax
>>> 
```

When assigning something to a variable using a `=`, the right side of
the `=` is always executed before the left side. This means that we can
do something with a variable on the right side, then assign the result
back to the same variable on the left side.

```py
>>> a = 1
>>> a = a + 1
>>> a
2
>>> 
```

To do something to a variable (for example, to add something to it) we
can also use `+=`, `-=`, `*=` and `/=` instead of `+`, `-`, `*` and
`/`. The "advanced" `%=`, `//=` and `**=` also work.

```py
>>> a += 2          # a = a + 2
>>> a -= 2          # a = a - 2
>>> a *= 2          # a = a * 2
>>> a /= 2          # a = a / 2
>>> 
```

This is not limited to integers.

```py
>>> a = 'hello'
>>> a *= 3
>>> a += 'world'
>>> a
'hellohellohelloworld'
>>> 
```

Now you also understand why typing hello to the prompt didn't work in
the beginning of this tutorial. But we can assign something to a
variable called hello and then type hello:

```py
>>> hello = 'hello there'
>>> hello
'hello there'
>>> 
```

## Booleans

There are two Boolean values, True and False. In Python, and in many
other programming languages, `=` is assigning and `==` is comparing.
`a = 1` sets a to 1, and `a == 1` checks if a equals 1.

```py
>>> a = 1
>>> a == 1
True
>>> a = 2
>>> a == 1
False
>>> 
```

`a == 1` is the same as `(a == 1) == True`, but `a == 1` is more
readable, so most of the time you shouldn't write `== True` anywhere.

```py
>>> a = 1
>>> a == 1
True
>>> (a == 1) == True
True
>>> a = 2
>>> a == 1
False
>>> (a == 1) == True
False
>>> 
```

## None

None is Python's "nothing" value. It behaves just like any other value,
and it's often used as a default value for different kinds of things.
We'll find a bunch of ways to use None later.

None's behavior on the interactive prompt might be a bit confusing at
first:

```py
>>> thingy = None
>>> thingy
>>> 
```

That was weird! We set thingy to None, but typing `thingy` didn't echo
back None.

This is because the prompt never echoes back None. That is handy,
because many things result in None, and it would be annoying to see
None coming up all the time.

If you want to see a None on the interactive prompt, use print:

```py
>>> print(thingy)
None
>>> 
```

## Other comparing operators

So far we've used `==`, but there are other operators also. At this
point, this list probably looks awfully long, but it's actually pretty
easy to learn.

| Usage     | Description                       | True examples         |
|-----------|-----------------------------------|-----------------------|
| `a == b`  | a is equal to b                   | `1 == 1`              |
| `a != b`  | a is not equal to b               | `1 == 2`              |
| `a > b`   | a is greater than b               | `2 > 1`               |
| `a >= b`  | a is greater than or equal to b   | `2 >= 1`, `1 >= 1`    |
| `a < b`   | a is less than b                  | `1 < 2`               |
| `a <= b`  | a is less than or equal to b      | `1 <= 2`, `1 <= 1`    |

We can also combine multiple comparisons. These are not always correct,
because a and b don't need to be Booleans. We'll learn more about that
later.

| Usage     | Description                               | True example                      |
|-----------|-------------------------------------------|-----------------------------------|
| `a and b` | a is True and b is True                   | `1 == 1 and 2 == 2`               |
| `a or b`  | a is True, b is True or they're both True | `False or 1 == 1`, `True or True` |

Another way to combine operations is chaining. For example, `a < b < c`
does the same thing as `a < b and b < c`.

`not` can be used for negations. If `value` is true, `not value` is
False, and if `value` is false, `not value` is True.

There's also `is`, but don't use it instead of `==` unless you know
what you are doing. We'll learn more about it later.

***

You may use this tutorial freely at your own risk. See [LICENSE](LICENSE).

[Previous](the-way-of-the-program.md) |
[Next](using-functions.md) |
[Back to the list of contents](README.md)
