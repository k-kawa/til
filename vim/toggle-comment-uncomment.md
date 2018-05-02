# How to toggle comment/uncomment lines

Let's start from the following shell script and imagine that the cursor is at the head of the first line.

```sh
echo 1
echo 2
echo 3
```

Let's comment out the three lines.

- Select lines with `ctrl-v` and `jj`
  - `ctrl-v` starts blockwise visual mode. http://vimdoc.sourceforge.net/htmldoc/visual.html
- start insert mode at the head of the line with `I`, type `# ` to comment out it and `ECS` to go back to normal mode.

```sh
# echo 1
# echo 2
# echo 3
```

Next, let's delete the leading `# ` inserted.

- Select the leading `# ` with `ctrl-v` and `jj`.
- Delete the selected column with `d`

