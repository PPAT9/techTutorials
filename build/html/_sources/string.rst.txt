=======
Strings
=======

String constants
----------------
are delimited with “ ” (double quotes) or ‘ ‘ (single quotes) ::

    >> h = “Hello World”
    >> h = ‘Hello World’

Multiline string
----------------
String constant can contain new line by using double quotes or single quotes::

    >> h = “”” Hi
        How are you”””

String Concatenation
--------------------
Use + sign to concate 2 strings::

    >> s = “hi”
    >> t =  “How are you”
    >> print(s + t)
    Hi How are you


Strings are Immutable
---------------------

String cannot be modified like in programming language (like c)::

    >> h = “Hello world”
    >> h[2] = ‘g’
    TypeError: ‘str’ object does not support item assignment.

String Indexing and Splicing
----------------------------

String can be indexed like in C::

    >> h = “hello world”
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

    >> print “There are %d orange in the basket” % 32
    There are 32 orange in the basket

    >> print “There are %d %s and %d %s in the basket” % (32, ‘orange’, 12, ‘apple’)
    There are 32 orange and 12 apple in the basket

=================================
Python Strings - Useful Functions
=================================

::

    S = “Jack and Jill”

capitalize()
------------

Capitalizes first letter of the string::

    >> s.capitalize()
    >> Jack And Jill

count(str, beg=0, end=len(string))
----------------------------------

Count how many times str occurs in a string or in a substring (if beg and end is given)::

    >> s.count(‘J’) 
    2

find(str, beg=0, end=len(string))
---------------------------------

Determine if str occurs in string or in a substring of string 
if starting index *beg* and ending index *end* are given return **index** if found else **-1**
::

    >> s.find(‘and’)
    >> 5
    >> s.find(‘j’)
    >> -1


