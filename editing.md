---
title: Editing
layout: default
---

# New File

A new file can be created in two ways:

- Open a non-existing file from the command line with emacs: `$ emacs
  my_new_file`.  This will open a new empty buffer.
- Create a new buffer in Emacs by typing `C-x b` name of the buffer
  `RET`.  This creates a new buffer you can edit.  You can then [save
  to a file](editing.html#save).

# Save

Use `C-x C-s` to save a buffer changes to a file.  If there is no file
associated to a buffer, the minibuffer will prompt for one.

# Copy-Paste

Copy-paste is easier to do with CUA mode active.  To activate CUA
mode, go to the _Options_ menu and make sure _Use CUA Keys_ is ticked.
To save, _Options_ → _Save Options_.  Another way of activiating it is
by adding the following to your [`init` file](init-file.html):

    (cua-mode t)

Once CUA mode is active, copy-paste functions are bound to the usual
keys:

- `C-c`: Copy
- `C-p`: Paste
- `C-x`: Cut

## Yank

Anything that’s “killed” is actually cut, and can be _yanked_ using
`C-y`.  You can cycle through the previous cut values using `M-y`
after `C-y` as many times as you need.

- `C-M-SPC M-w` : Select current sexp, and put it in the kill ring.

# Delete and insert

- `C-k` : kill text to the end of line
- `C-w` : Kill [region](select.html)
- `M-d`: Delete word.
- `C-o`: Insert a newlie.
- `C-x C-o`: Delete blank lines, leaving one.
- `C-d`: `delete-char`, Deletes the next character.  `C-u C-d` deletes
  all spaces up to next char.
- `M-x flush-lines RET <regexp> RET`: Delete all the lines that match
  the regexp

# Sorting

- `M-x sort-lines`: Sort lines.
- `M-x reverse-region`: Reverse order of lines in region.

# Join Lines

- `M-^`: Join current line to previous, removing spaces.

# Delete all the empty lines

- `M-x flush-lines RET ^$ RET` on the current region.

# Delete duplicate lines

- `M-x delete-duplicate-lines`: Remove duplicate lines.
- `C-u M-| uniq`: Run `uniq` command on region.

# Undo-Redo

- `C-_` : undo
- `C-g C-_` : Redo after undo
- `C-g C-/` : Redo after undo

When CUA mode is active, `C-z` also acts as undo.

See also the [Emacs Manual](http://www.gnu.org/software/emacs/manual/html_node/emacs/Undo.html).

# Formatting

- `M-c` : capitalize word
- `M-u` : uppercase word
- `M-l` : lowercase word
- `M-x center-line` : center the text on the line.
- `M-^`: join two lines, removing the extra space.
- `C-t`: transpose character
- `M-t`: transport words
- `C-x C-t`: transpose lines
- `M-x toggle-truncate-lines`: toggle line wrapping.
- `M-SPC`: `just-one-space`. Delete all white spaces until the next
  non-space char, leaving just one.
- `C-x TAB`: `indent-rigidly`.  Indentation of region can be adjusted
  with <left>, <right>, <S-left>, <S-right>.

# Unicode

- `C-x 8 RET`: Enters Unicode character by entering its name,
  e.g. `C-x 8 RET RIGHTWARDS ARROW RET`

Next: [Search](search.html)
