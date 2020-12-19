# Python packaging example

**Contact**: Robert Nowotniak <<rnowotniak@gmail.com>>

This is a simple example package. 

References:
* https://packaging.python.org/tutorials/packaging-projects/
* https://realpython.com/pypi-publish-python-package/

## Usage

Update `version` variable in `setup.py`

Rebuild the package (source and dist):

    python setup.py sdist bdist_wheel

Then, run:

    python -m twine upload -r testpypi dist/example*

Upload result:

    $ python -m twine upload -r testpypi dist/example*
    Uploading distributions to https://test.pypi.org/legacy/
    Enter your username: __token__
    Enter your password: *******************
    Uploading example_pkg_rnowotniak-0.0.3-py3-none-any.whl
    100%|███████████████████████████████████
    Uploading example-pkg-rnowotniak-0.0.3.tar.gz
    100%|███████████████████████████████████
    
    View at:
    https://test.pypi.org/project/example-pkg-rnowotniak/0.0.3/

Installing the package:

    $ pip install --user --upgrade -i https://test.pypi.org/simple/ example-pkg-rnowotniak 
    Looking in indexes: https://test.pypi.org/simple/
    Collecting example-pkg-rnowotniak
      Downloading https://test-files.pythonhosted.org/packages/42/f2/f1f308cc4f49c6fd8ae432cb1c06b0b88d21feb0f79fcb52cb5d9ada48c7/example_pkg_rnowotniak-0.0.3-py3-none-any.whl (2.5 kB)
    Installing collected packages: example-pkg-rnowotniak
    Successfully installed example-pkg-rnowotniak-0.0.3
    
    $ python
    Python 3.9.0 (default, Oct  7 2020, 23:09:01) 
    [GCC 10.2.0] on linux
    Type "help", "copyright", "credits" or "license" for more information.
    >>> import example_pkg
    test!
    >>> 

