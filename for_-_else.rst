``for/else``
------------

Loops are an integral part of any language. Likewise ``for`` loops are
an important part of Python. However there are a few things which most
beginners do not know about them. We will discuss a few of them one-by-one.

Let's first start off with what we know. We know that we can use ``for`` loops
like this:

.. code:: python

    fruits = ['apple', 'banana', 'mango']
    for fruit in fruits:
        print(fruit.capitalize())

    # Output: Apple
    #         Banana
    #         Mango

That is the very basic structure of a ``for`` loop. Now let's move on to
some of the lesser known features of ``for`` loops in Python.

``else`` Clause
^^^^^^^^^^^^^^^

``for`` loops also have an ``else`` clause which most of us are unfamiliar
with. The ``else`` clause executes after the loop completes normally.
This means that the loop did not encounter a ``break`` statement. They are
really useful once you understand where to use them. I, myself, came to
know about them a lot later.

The common construct is to run a loop and search for an item. If the
item is found, we break out of the loop using the ``break`` statement. There are two
scenarios in which the loop may end. The first one is when the item is
found and ``break`` is encountered. The second scenario is that the loop
ends without encountering a ``break`` statement. Now we may want to know which one of these is the reason for a
loop's completion. One method is to set a flag and then check it once the
loop ends. Another is to use the ``else`` clause.

This is the basic structure of a ``for/else`` loop:

.. code:: python

    for item in container:
        if search_something(item):
            # Found it!
            process(item)
            break
    else:
        # Didn't find anything..
        not_found_in_container()

Consider this simple example which I took from the official
documentation:

.. code:: python

    for n in range(2, 10):
        for x in range(2, n):
            if n % x == 0:
                print(n, 'equals', x, '*', n/x)
                break

It finds factors for numbers between 2 to 9. Now for the fun part. We
can add an additional ``else`` block which catches the numbers which have no factors and are therefore prime numbers:

.. code:: python

    for n in range(2, 10):
        for x in range(2, n):
            if n % x == 0:
                print( n, 'equals', x, '*', n/x)
                break
        else:
            # loop fell through without finding a factor
            print(n, 'is a prime number')
