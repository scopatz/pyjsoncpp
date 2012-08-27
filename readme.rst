PyJsonCpp: Python bindings for JsonCpp
=======================================
The `JsonCpp project`_ provides an excellent in-memory JSON data structure as well 
as string writers and parsers.  Here are Python bindings for JsonCpp using Cython.

.. _JsonCpp project: http://jsoncpp.sourceforge.net/

.. _install:

============
Installation
============
Installing PyJsonCpp from source is easy.  First, download or clone
this repository.  Then run the setup commands from the base directory::

    cd pyne/
    python setup.py install --user

These bindings require on Cython v0.17+.  The tests rely on nose.


=============
Usage Example
=============
The Value object is the main interface for 
Values may be converted to and from regular Python types.  These have the 
normal behaviour for their type.

.. code-block:: python

    >>> from jsoncpp import Value, Reader, FastWriter, StyledWriter

    >>> v = Value({'name': 'Terry Jones', 'age': 42.0})
    >>> v['quest'] = "To find the grail."
    >>> v.keys()
    ['age', 'name', 'quest']
    >>> v['name']
    'Terry Jones'

    >>> v = Value([1, 2, 5, 3])
    >>> v[1:-1]
    [2, 5]
    >>> v[1:-1] = [42, 65]
    >>> v
    [1, 42, 65, 3]

    >>> v = Value("No one expects the Spanish Inquisition!!!!")
    >>> len(v)
    42



