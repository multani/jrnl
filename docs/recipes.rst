.. _recipes:

FAQ
===

Recipes
-------

Co-occurrence of tags
~~~~~~~~~~~~~~~~~~~~~

If I want to find out how often I mentioned my flatmates Alberto and Melo in the same entry, I run ::

    jrnl @alberto --tags | grep @melo

And will get something like ``@melo: 9``, meaning there are 9 entries where both ``@alberto`` and ``@melo`` are tagged. How does this work? First, ``jrnl @alberto`` will filter the journal to only entries containing the tag ``@alberto``, and then the ``--tags`` option will print out how often each tag occurred in this `filtered` journal. Finally, we pipe this to ``grep`` which will only display the line containing ``@melo``.

Combining filters
~~~~~~~~~~~~~~~~~

You can do things like ::

    jrnl @fixed -starred -n 10 -until "jan 2013" --short

To get a short summary of the 10 most recent, favourited entries before January 1, 2013 that are tagged with ``@fixed``.

Known Issues
------------

- The Windows shell prior to Windows 7 has issues with unicode encoding. If you want to use non-ascii characters, change the codepage with ``chcp 1252`` before using `jrnl` (Thanks to Yves Pouplard for solving this!)
- _jrnl_ relies on the `PyCrypto` package to encrypt journals, which has some known problems with installing on Windows and within virtual environments.
