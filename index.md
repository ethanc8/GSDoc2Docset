# GSDoc2Docset

Converts autogsdoc-generated API documentation to a docset.

See [Dependencies](Dependencies.md) to install the dependencies.

This project does not have any code -- it's entirely Markdown and JSON (except for the Workspaces).

## Tutorial

1. Create a folder in "Workspaces". Example:
```bash
cd Workspaces
mkdir FoobarKit
cd FoobarKit
```

2. Copy your documentation into this folder.
3. Create a `dashing.json` file:
```bash
dashing create
```

4. Open `dashing.json` and replace it with the following:
```json
{
    "name": "GNUstep Foobar Kit",
    "package": "FoobarKit",
    "index": "Reference/FoobarKit.html",
    "selectors": {
        "a[name^=method\\$]": "Method",
        "a[name^=constant\\$]": "Constant",
        "a[name^=class\\$]": "Class",
        "a[name^=type\\$]": "Type",
        "a[name^=function\\$]": "Function",
        "a[name^=macro\\$]": "Macro",
        "a[name^=variable\\$]": "Variable",
        "a[name^=title\\$]": "Guide",
        "a[name^=ivariable\\$]": "Value"
    },
    "ignore": [
    ],
    "icon32x32": "",
    "allowJS": false,
    "ExternalURL": ""
}
```

5. Edit the properties to best fit your use case.
6. Build the docset:
```bash
dashing build
```

7. Install the docset into Zeal. Example:
```bash
cp -r FoobarKit.docset ~/.local/share/Zeal/Zeal/docsets
```

## Notes

* Why GSDoc instead of ETDocGen?
    * ETDocGen doesn't have easily-parseable HTML output.
* Manuals are not currently included, because I'm planning to migrate them to Sphinx.