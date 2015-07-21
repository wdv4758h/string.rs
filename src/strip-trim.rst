========================================
Remove Leading and Trailing Characters
========================================

Python strip & Rust trim
========================================

Spaces
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "    sqeeze me    "

    # Get Result

    result = s.strip()


.. code-block:: rust

    // Rust

    // Setup

    let s = "    sqeeze me    ";

    // Get Result

    let result = s.trim();


Any Character
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "~~~~sqeeze me~~~~"

    # Get Result

    result = s.strip("~")


.. code-block:: rust

    // Rust

    // Setup

    let s = "~~~~sqeeze me~~~~";

    // Get Result

    let result = s.trim_matches('~');


Any Character"s"
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "~!~!sqeeze me!~!~"

    # Get Result

    result = s.strip("~!")


.. code-block:: rust

    // Rust

    // Setup

    let s = "~!~!sqeeze me!~!~";

    // Get Result

    let patterns : &[_] = &['~', '!'];
    let result = s.trim_matches(patterns);


Complex Condition
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "9876sqeeze me5432"

    # Get Result

    def strip_func(data, func):

        length = len(data)

        for start, c in enumerate(data):
            if not func(c):
                break

        if start == length-1:
            return ""

        for end, c in enumerate(reversed(data[start:])):
            if not func(c):
                break

        return data[start:length-end]

    result = strip_func(s, lambda c: c.isnumeric())


.. code-block:: rust

    // Rust

    // Setup

    let s = "9876sqeeze me5432";

    // Get Result

    let result = s.trim_matches(|c: char| c.is_numeric());
    let result = s.trim_matches(char::is_numeric);


Python lstrip & Rust trim_left
========================================

Spaces
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "    sqeeze me"

    # Get Result

    result = s.lstrip()


.. code-block:: rust

    // Rust

    // Setup

    let s = "    sqeeze me";

    // Get Result

    let result = s.trim_left();


Any Character
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "~~~~sqeeze me"

    # Get Result

    result = s.lstrip("~")


.. code-block:: rust

    // Rust

    // Setup

    let s = "~~~~sqeeze me";

    // Get Result

    let result = s.trim_left_matches('~');


Any Character"s"
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "~!~!sqeeze me"

    # Get Result

    result = s.lstrip("~!")


.. code-block:: rust

    // Rust

    // Setup

    let s = "~!~!sqeeze me";

    // Get Result

    let patterns : &[_] = &['~', '!'];
    let result = s.trim_left_matches(patterns);


Complex Condition
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "9876sqeeze me"

    # Get Result

    def strip_func(data, func):

        for start, c in enumerate(data):
            if not func(c):
                break

        return data[start:]

    result = strip_func(s, lambda c: c.isnumeric())


.. code-block:: rust

    // Rust

    // Setup

    let s = "9876sqeeze me";

    // Get Result

    let result = s.trim_left_matches(|c: char| c.is_numeric());
    let result = s.trim_left_matches(char::is_numeric);


Python rstrip & Rust trim_right
========================================

Spaces
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "sqeeze me    "

    # Get Result

    result = s.rstrip()


.. code-block:: rust

    // Rust

    // Setup

    let s = "sqeeze me    ";

    // Get Result

    let result = s.trim_right();


Any Character
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "sqeeze me~~~~"

    # Get Result

    result = s.rstrip("~")


.. code-block:: rust

    // Rust

    // Setup

    let s = "sqeeze me~~~~";

    // Get Result

    let result = s.trim_right_matches('~');


Any Character"s"
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "sqeeze me!~!~"

    # Get Result

    result = s.rstrip("~!")


.. code-block:: rust

    // Rust

    // Setup

    let s = "sqeeze me!~!~";

    // Get Result

    let patterns : &[_] = &['~', '!'];
    let result = s.trim_right_matches(patterns);


Complex Condition
------------------------------

Result : "sqeeze me"

.. code-block:: python

    # Python

    # Setup

    s = "sqeeze me5432"

    # Get Result

    def strip_func(data, func):

        for end, c in enumerate(reversed(data)):
            if not func(c):
                break

        return data[:len(data)-end]

    result = strip_func(s, lambda c: c.isnumeric())


.. code-block:: rust

    // Rust

    // Setup

    let s = "sqeeze me5432";

    // Get Result

    let result = s.trim_right_matches(|c: char| c.is_numeric());
    let result = s.trim_right_matches(char::is_numeric);
