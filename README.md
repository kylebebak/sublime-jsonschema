# _jsonschema_ module as a Package Control dependency

This is the [jsonschema](https://github.com/Julian/jsonschema) module bundled for use with Sublime Text's Package Control.

It's currently 3 commits ahead of [v2.6.0](https://github.com/Julian/jsonschema/releases/tag/v2.6.0).

Read about [dependencies](https://packagecontrol.io/docs/dependencies).


## Gotchas
The plugin will not work without the following file: `/all/jsonschema/_version.py`. This file is automatically generated by `setup.py` when the package is installed, e.g. via PyPI. The file is not in version control, which means you won't be able to copy it from the GitHub repo.

I installed the plugin from PyPI, found this file, and copied it over to the `/all/jsonschema/` directory.


## License
The contents of the root folder in this repository are released under the __public domain__. The contents of the `all/` folder are under __their own bundled licenses__.
