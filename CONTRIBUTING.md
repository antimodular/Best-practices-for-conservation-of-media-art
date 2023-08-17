# Contributing

Thank you for your interest in contributing to this work.

The current ongoing task would be to translate the work.

## Translating using Sphinx and sphinx-intl

### Install

```
pip install -r requirements.txt
```

### Create .po file

Create the `.po` file for a new locale:

```
make gettext
sphinx-intl update -p build/gettext -l es -l fr -l de
```

### Create .md file from the .po file

Create or update a .md file from the translated .po file:

```
sphinx-build -b html -D language=en source public/
sphinx-build -b html -D language=es source public/es
sphinx-build -b html -D language=fr source public/fr
sphinx-build -b html -D language=de source public/de
```

### Update the .po file

If the original `.md` file was changed, you may want to update its translation.

To update the  `.po` file:

```
sphinx-intl update -p build/gettext
```

You can now check the translation for entries tagged as `fuzzy` and update them as needed.

To update the `.md` file, see the *Create .md file from the .po file* section.


### References

* the sphinx doc on [sphinx-intl](https://www.sphinx-doc.org/en/master/usage/advanced/intl.html)
