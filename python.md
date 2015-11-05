# Python

## Python shell - common imports

When working in the python shell, importing common imports from a file
say `my_imports.py`:

    from myapp import db, User

Then after getting into the python shell do:

    python
	>> execfile('my_imorts.py')

or (not sure if this is the right way):

    python -i my_imports.py

