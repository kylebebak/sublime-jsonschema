# *jsonschema* module for Package Control
[![Build Status](https://travis-ci.org/packagecontrol/jsonschema.png?branch=master)](https://travis-ci.org/packagecontrol/jsonschema)


This is the *[jsonschema][]* module
bundled for usage with [Package Control][],
a package manager
for the [Sublime Text][] text editor.


this repo | pypi
---- | ----
![latest tag](https://img.shields.io/github/tag/packagecontrol/jsonschema.svg) | [![pypi](https://img.shields.io/pypi/v/jsonschema.svg)][pypi]


## How to use *jsonschema* as a dependency

In order to tell Package Control
that you are using the *jsonschema* module
in your ST package,
create a `dependencies.json` file
in your package root
with the following contents:

```js
{
   "*": {
      "*": [
         "sublime-jsonschema"
      ]
   }
}
```

If the file exists already,
add the above entry to the very dependency list.

Then run the **Package Control: Satisfy Dependencies** command
to make Package Control
install the module for you locally
(if you don't have it already).

After all this
you can use `import jsonschema`
in any of your Python plugins.

## Example use

In the example below we validate settings, which is an important use case.

```
from jsonschema.validators import validate
from jsonschema.exceptions import ValidationError
...

schema = sublime.decode_value(sublime.load_resource("path/to/schema_file.json"))
settings = sublime.decode_value(sublime.load_resource("path/to/my_plugin.sublime-settings"))

try:
    validate(merged_settings, schema)
except ValidationError as ve:
    print("Settings invalid.")
else:
    print("Settings valid.")

```

See also:
[Documentation on Dependencies](https://packagecontrol.io/docs/dependencies)


## How to update this repository (for contributors)

1. Download the latest tarball
   from [pypi][].
2. Delete everything inside the `all/` folder.
3. Copy the `jsonschema/` folder
   and everything related to copyright/licensing
   from the tarball
   to the `all/` folder.
4. Adapt import paths for all python files.
5. Commit changes
   and either create a pull request
   or create a tag directly
   in the format `v<version>`
   (in case you have push access).


## License

The contents of the root folder
in this repository
are released
under the *public domain*.
The contents of the `all/` folder
fall under *their own bundled licenses*.


[jsonschema]: https://python-jsonschema.readthedocs.io/en/latest/
[Package Control]: http://packagecontrol.io/
[Sublime Text]: http://sublimetext.com/
[pypi]: https://pypi.python.org/pypi/jsonschema
