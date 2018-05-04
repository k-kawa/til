# xpath misc

## Links
- http://manpages.ubuntu.com/manpages/xenial/man1/xpath.1p.html
- https://stackoverflow.com/questions/15461737/how-to-execute-xpath-one-liners-from-shell

# Install xmllint

`xmllint` is included in `libxml2-util` package.

ihttp://xmlsoft.org/xmllint.html

```zsh
sudo apt-get install libxml2-utils
```

```zsh
xmllint --html --xpath '//foo/bar' your.html
```
