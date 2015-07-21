========================================
Separate Strings by Specific Separators
========================================

Python split & Rust split_whitespace
========================================

by Whitespace (no upper bound)
------------------------------

result : ["some", "useful", "data"]

.. code-block:: python

    # Python

    # Setup

    s = "    some useful data    "

    # Get Result

    result = s.split()


.. code-block:: rust

    // Rust

    // Setup

    let s = "    some useful data    ";

    // Get Result

    // .split_whitespace() will return an iterator

    let result : Vec<_> = s.split_whitespace().collect();
    let result : Vec<&str> = s.split_whitespace().collect();


Notice: If you use .split(' ') in Rust, you will get a different result. Like this :

.. code-block:: python

    # Python

    s.split(" ")    # ["", "", "", "", "some", "useful", "data", "", "", "", ""]

.. code-block:: rust

    // Rust

    let result : Vec<_> = s.split(' ').collect();       // ["", "", "", "", "some", "useful", "data", "", "", "", ""]
    let result : Vec<&str> = s.split(' ').collect();    // ["", "", "", "", "some", "useful", "data", "", "", "", ""]


by Whitespace (with upper bound)
--------------------------------

result : ["some", "useful data    "]

.. code-block:: python

    # Python

    # Setup

    s = "    some useful data    "

    # Get Result

    result = s.split(maxsplit=1)


.. code-block:: rust

    // Rust

    // Setup

    let s = "    some useful data    ";

    // Get Result

    [TODO]


Python split & Rust split
========================================

by Any Character (no upper bound)
---------------------------------

result : ["col1", "col2", "col3", "col4"]

.. code-block:: python

    # Python

    # Setup

    s = "col1,col2,col3,col4"

    # Get Result

    result = s.split(',')


.. code-block:: rust

    // Rust

    // Setup

    let s = "col1,col2,col3,col4";

    // Get Result

    let result: Vec<_> = s.split(',').collect();


by Any Character"s" (no upper bound)
------------------------------------

result : ["col1", "", "col2", "", "col3", "", "col4"]

.. code-block:: python

    # Python

    # Setup

    s = "col1!?col2?!col3!?col4"

    # Get Result

    [TODO]


.. code-block:: rust

    // Rust

    // Setup

    let s = "col1!?col2?!col3!?col4";

    // Get Result

    let result: Vec<_> = s.split(|c: char| "!?".contains(c)).collect();
    let result: Vec<_> = s.split(|c: char| str::contains("?!", c)).collect();


by Any String (no upper bound)
------------------------------

result : ["col1", "col2", "col3", "col4"]

.. code-block:: python

    # Python

    # Setup

    s = "col1::col2::col3::col4"

    # Get Result

    result = s.split("::")


.. code-block:: rust

    // Rust

    // Setup

    let s = "col1::col2::col3::col4";

    // Get Result

    let result: Vec<_> = s.split("::").collect();


by Any String"s" (no upper bound)
---------------------------------

result : ["col1", "col2", "col3", "col4"]

.. code-block:: python

    # Python

    # Setup

    s = "col1//col2::col3%%col4"

    # Get Result

    [TODO]


.. code-block:: rust

    // Rust

    // Setup

    let s = "col1//col2::col3%%col4";

    // Get Result

    [TODO]


by Complex Condition (no upper bound)
-------------------------------------

by Regular Expression (no upper bound)
--------------------------------------

Python split & Rust splitn
========================================

by Any Character (with upper bound)
-----------------------------------

result : ["col1", "col2", "col3,col4"]

.. code-block:: python

    # Python

    # Setup

    s = "col1,col2,col3,col4"

    # Get Result

    result = s.split(',', 2)    # maxsplit = 2, max length is 3


.. code-block:: rust

    // Rust

    // Setup

    let s = "col1,col2,col3,col4";

    // Get Result

    let result: Vec<_> = s.splitn(3, ',').collect();    // count = 3, max length is 3


by Any Character"s" (with upper bound)
--------------------------------------

result : ["col1", "", "col2", "", "col3!?col4"]

.. code-block:: python

    # Python

    # Setup

    s = "col1!?col2?!col3!?col4"

    # Get Result

    [TODO]


.. code-block:: rust

    // Rust

    // Setup

    let s = "col1!?col2?!col3!?col4";

    // Get Result

    let result: Vec<_> = s.splitn(5, |c: char| "!?".contains(c)).collect();         // count = 3, max length is 3
    let result: Vec<_> = s.splitn(5, |c: char| str::contains("?!", c)).collect();


by Any String (with upper bound)
--------------------------------

result : ["col1", "col2", "col3::col4"]

.. code-block:: python

    # Python

    # Setup

    s = "col1::col2::col3::col4"

    # Get Result

    result = s.split("::", 2)   # maxsplit = 2, max length is 3


.. code-block:: rust

    // Rust

    // Setup

    let s = "col1::col2::col3::col4";

    // Get Result

    let result: Vec<_> = s.splitn(3, "::").collect();   // count = 3, max length is 3


by Any String"s" (with upper bound)
-----------------------------------

by Complex Condition (with upper bound)
---------------------------------------

by Regular Expression (with upper bound)
----------------------------------------

Python rsplit & Rust rsplit
========================================

Python rsplit & Rust rsplitn
========================================

Python splitlines & Rust lines
========================================

result : ["We", "Are", "The", "World", "", "!!!"]

.. code-block:: python

    # Python

    # Setup

    s = "We\nAre\nThe\nWorld\n\n!!!"

    # Get Result

    result = s.splitlines()


.. code-block:: rust

    // Rust

    // Setup

    let s = "We\nAre\nThe\nWorld\n\n!!!";

    // Get Result

    let result: Vec<_> = s.lines().collect();
