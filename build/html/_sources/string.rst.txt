=======
Strings
=======

String constants
----------------
are delimited with "" (double quotes) or ' ' (single quotes) ::

    >> h = "Hello World"
    >> h = 'Hello World'

Multiline string
----------------
String constant can contain new line by using double quotes or single quotes::

    >> h = """Hi
        How are you"""

String Concatenation
--------------------
Use + sign to concate 2 strings::

    >> s = "hi"
    >> t =  "How are you"
    >> print(s + t)
    Hi How are you


Strings are Immutable
---------------------

String cannot be modified like in programming language (like c)::

    >> h = "Hello world"
    >> h[2] = 'g'
    TypeError: 'str' object does not support item assignment.

String Indexing and Slicing
----------------------------

String can be indexed like in C::

    >> h = "hello world"
    >> h[0]  	# note index starts from zero
    H

String can be sliced::

    >>h[2:5]
    llo
    >>h[2:]
    llo world
    >>h[:2]
    he

String Interpolation
--------------------

The mod(%) operator in string is used for formatting or to insert variable in a string::

    >> print "There are %d orange in the basket" % 32
    There are 32 orange in the basket

    >> print "There are %d %s and %d %s in the basket" % (32, 'orange', 12, ‘apple’)
    There are 32 orange and 12 apple in the basket

==========================
Strings - Useful Functions
==========================

::

    S = "Jack and Jill"

capitalize
------------

Capitalizes first letter of the string
::

    >> s.capitalize()
    Jack And Jill

count
-----

count(str, start=0, end=len(string))
Count how many times str occurs in a string or in a substring (if start and end is given)::

    >> s.count('J')
    2
    >> s.count("J", 0, 5)
    1

encode
------

The encode() method encodes the string, using the specified encoding.
If no encoding is specified, UTF-8 will be used.
string.encode(encoding=encoding, errors=errors)
encoding	Optional. A String specifying the encoding to use. Default is UTF-8
errors	    Optional. A String specifying the error method. Legal values are:
* 'backslashreplace'	- uses a backslash instead of the character that could not be encoded
* 'ignore'	- ignores the characters that cannot be encoded
* 'namereplace'	- replaces the character with a text explaining the character
* 'strict'	- Default, raises an error on failure
* 'replace'	- replaces the character with a questionmark
* 'xmlcharrefreplace'	- replaces the character with an xml character

::

    >>txt = "My name is Ståle"

    >>print(txt.encode(encoding="ascii",errors="backslashreplace"))
    b'My name is St\\xe5le'
    >>print(txt.encode(encoding="ascii",errors="ignore"))
    b'My name is Stle'
    >>print(txt.encode(encoding="ascii",errors="namereplace"))
    b'My name is St\\N{LATIN SMALL LETTER A WITH RING ABOVE}le'
    >>print(txt.encode(encoding="ascii",errors="replace"))
    b'My name is St?le'
    >>print(txt.encode(encoding="ascii",errors="xmlcharrefreplace"))
    b'My name is St&#229;le'
    >>print(txt.encode(encoding="ascii",errors="strict"))
    Traceback (most recent call last):
    File "demo_ref_string_encode2,py", line 8, in <module>
    UnicodeEncodeError: 'ascii' codec can't encode character '\xe5\ in position 13: ordinal not in range(128)

find
----

find(str, beg=0, end=len(string))

Determine if str occurs in string or in a substring of string
if starting index *beg* and ending index *end* are given return **index** if found else **-1**

::

    >> s.find('and')
    5
    >> s.find('j')  # small j does not exist to will return -1
    -1


len
---

Return the length of the string

::

    >> s.len()
    >> 13

strip
-----

Remove all trailing and leading white space
::

    >> line =  " hi I am with space "
    >> line.stripp()
    >> hi I am with space

split
-----

Splits string according to delimiter str (space if not provided)
and return list of substrings: split into at most num substrings.
::

    >> s.split()
    >> [‘Jack’, ‘and’, ‘Jill’]

    >>a = "Tim|John|Jake"
    >>a.split(",")
    >>["Tim", "John", "Jake"]

join
----

Merges (concatenates) the string representations of elements in sequence.
Take input as list or tuple or set

::

    >> " ".join([‘Jack’, ‘and’, ‘Jill’])
    >> Jack and Jill

replace
-------

Replaces all occurrences of old in string with new or at most max occurrence if max given
::

    >> value = “aabc”
    >> print(value.replace(‘bc’, ‘yz’))
    >> aayz
    >> print(value.replace(‘a’, ‘x’, 1))  # replace only first occurance
    >> xabc


startswith
----------

string.startswith(value, start, end)
The startswith() method returns *True*
if the string starts with the specified value, otherwise *False*.

::

    >>s.startswith("Jack")
    True
    >>s.startswith("and", 5)


splitlines
----------

Split a string into a list where each line is a list item
The splitting is done at line breaks.

::

    >>txt = "line one \nsecond line \n thrid line"
    >>txt.splitlines()
    line one
    second line
    third line
