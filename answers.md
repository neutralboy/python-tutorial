# Answers

These are answers for exercises in the chapters. In programming, there's always more than one way to do things, so if your solution wasn't exactly like mine it's not necessarily wrong. Some Python users say that there should be only one right way, but that goal will never be fully reached.

## ThinkPython: The way of the program

1. With +, the strings get added together, and with * we get an error.
2. With + we get an error, and with * the string is repeated multiple times.
3. Python calculates the result and echoes it.

## Using if, else and elif

1. Just ask the word and print word * 1000.

    ```py
    word = input("Enter a word: ")
    print(word * 1000)
    ```

2. Add a space to the word before printing.

    ```py
    word = input("Enter a word: ")
    word += " "
    print(word * 1000)
    ```

    We can also add the space right away on the first line:

    ```py
    word = input("Enter a word: ") + " "
    print(word * 1000)
    ```

    Of course, there are 999 spaces between 1000 words and this will
    print 1000 spaces instead, so there will be a useless space at the
    end, but it doesn't matter. If we really want to get rid of the
    space, we can do something like this instead:

    ```py
    no_space = input("Enter a word: ")
    yes_space = no_space + " "
    print(yes_space * 999 + no_space)
    ```

3. Like this:

    ```py
    first = input("Enter a word: ")
    second = input("Enter another word: ")
    words = first + " " + second + " "
    print(words * 1000)
    ```

4. You can compare the word against an empty string (`""` or `''`) to
    check if it's empty. In this example, the password is "secret".

    ```py
    word = input("Enter your password: ")

    if word == "secret":
        print("Welcome!")
    elif word == "":
        print("You didn't enter anything.")
    else:
        print("Access denied.")
    ```

5. Simply check the username first, then the password in indented
    blocks of code.

    ```py
    username = input("Enter your username: ")
    password = input("Enter your password: ")

    if username == "foo":
        if password == "biz":
            print("Welcome foo!")
        else:
            print("Wrong password!")
    elif username == "bar":
        if password == "baz":
            print("Welcome bar!")
        else:
            print("Wrong password!")
    else:
        print("Wrong username.")
    ```

    Example output:

    ```
    >>> ================================ RESTART ================================
    >>> 
    Enter your username: foo
    Enter your password: biz
    Welcome foo!
    >>> ================================ RESTART ================================
    >>> 
    Enter your username: bar
    Enter your password: baz
    Welcome bar!
    >>> ================================ RESTART ================================
    >>> 
    Enter your username: spam
    Enter your password: eggs
    Wrong username.
    >>> ================================ RESTART ================================
    >>> 
    Enter your username: foo
    Enter your password: lol
    Wrong password!
    >>> 
    ```

## Loops

1. For loop over the users, each user is a list that contains a
    username and a password.

    ```py
    users = [
        ['foo', 'biz'],
        ['bar', 'baz'],
    ]

    username = input("Username: ")
    password = input("Password: ")

    logged_in = False
    for user in users:
        if username == user[0] and password == user[1]:
            logged_in = True
            break

    if logged_in:
        print("Welcome, " + username + "!")
    else:
        print("Wrong username or password.")
    ```

2. Just put the whole thing in a `while True:`. Remember that a break
    will always break the innermost loop it's in.

    ```py
    users = [
        ['foo', 'biz'],
        ['bar', 'baz'],
    ]

    while True:
        username = input("Username: ")
        password = input("Password: ")

        logged_in = False
        for user in users:
            if username == user[0] and password == user[1]:
                logged_in = True
                break   # break the for loop

        if logged_in:
            print("Welcome, " + username + "!")
            break   # break the while loop
        else:
            print("Wrong username or password.")
    ```

3. Add a for loop that works as an attempt counter.

    ```py
    users = [
        ['foo', 'biz'],
        ['bar', 'baz'],
    ]

    for attempts_left in [3, 2, 1, 0]:
        if attempts_left == 0:
            print("No attempts left!")
            break   # break the outer for loop

        print(attempts_left, "attempts left.")
        username = input("Username: ")
        password = input("Password: ")

        logged_in = False
        for user in users:
            if username == user[0] and password == user[1]:
                logged_in = True
                break   # break the inner for loop

        if logged_in:
            print("Welcome, " + username + "!")
            break   # break the outer for loop
        else:
            print("Wrong username or password.")
    ```

## Defining functions

1. Use `-value` to get tha negative in the abs function, and for loops
    in the other two functions.

    ```py
    def my_abs(value):
        if value < 0:
            return -value
        # actually, this else is useless because returning ends the
        # function anyway
        else:
            value

    def my_any(a_list):  # don't call this "list", see summary in the Lists chapter
        for item in a_list:
            if item:
                return True    # ends the function
        return True

    def my_all(a_list):
        for item in a_list:
            if not item:
                return False
        return True
    ```

2. Like this:

    ```py
    def box(message, character='*'):
        number_of_characters = len(message) + 4
        print(character * number_of_characters)
        print(message)
        print(character * number_of_characters)
    ```

***

You may use this tutorial freely at your own risk. See [LICENSE](LICENSE).

[Back to the list of contents](README.md)
