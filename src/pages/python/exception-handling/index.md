Within Python, exceptions are raised by the interpreter in the event of an error. These exceptions come in many shapes and forms. An example of such would be to trying to convert a non-integer string into an integer, which throws an `ValueError`:

    >>> a = "twelve"  # Not an integer
    >>> int(a)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    ValueError: invalid literal for int() with base 10: 'twelve'
    
These errors can be handled with `try` and `except` blocks. The syntax of such blocks is quite similar to `if-else` blocks. In order to catch an exception properly, declare the exception-prone code within the `try` block, and handle the specified exception within the `except` block. An example to handle the `ValueError` above would be as following:

    a = input("Enter an integer: ")
    # "Try" to convert the current value of a (a string) into an integer
    try:
        a = int(a)
    # If an error is thrown and it is a ValueError
    except ValueError:
        print("That was not an integer!")

In addition to utilizing the `try` and the `except` blocks, there is also an optional `else` block that could be used after the sequence. Code within the `else` block would be executed if the code within the `try` block does not raise an error. For example, as an extension of the above case:

    a = input("Enter an integer: ")
    try:
        a = int(a)
    except ValueError:
        print("That was not an integer!")
    else:
        a += 1
        
Using the `else` block is, in general, better practice than putting such code within the `try` block, as it reduces the possibility of the code within the `else` block throwing an exception not intended to be caught to be handled.
