# Python

## Using relative imports in a script.

Assume the following project:

    myproject
	  mydir
	    run.py
	    file.py

run.py:

    from .file import x
    print 'x is {}'.format(x)

file.py:

    x = 4

Executing run.py gives an error

    $ python mydir/run.py 
    Traceback (most recent call last):
      File "mydir/run.py", line 1, in <module>
        from .file import x
    ValueError: Attempted relative import in non-package

Instead execute it as (Note the `.` instead of `/` separator and no `.py` extension:

    $ python -m mydir.run
    x is 4

For more infor see [this stackoverflow discussion](http://stackoverflow.com/questions/11536764/attempted-relative-import-in-non-package-even-with-init-py/27876800#27876800)

## Python shell - common imports

In the python shell, it may become inconvenient to manually import some
symbols each time you run the python shell.

For convenience, you can import these in a file say `my_imports.py`:

    from myapp import db, User

Then, in the python shell do:

    python
	>> execfile('my_imorts.py')

or run the python shell as (not sure if this is the right way):

    python -i my_imports.py

