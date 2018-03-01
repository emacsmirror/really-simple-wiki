# Really Simple Wiki Mode

This is the simplest of all the wiki modes. All it does is add a
keybinding to insert some tags, and the hilighting of tags plus
WikiNames. If you are editing wiki pages within Emacs, this is quite
elegant.

The original Simple Wiki Mode got incorporated into Emacs Http.

## Usage

This requires two steps:

Getting the wiki page into Emacs: Some browsers allow you to define an
external editor for text areas. This is where you must set `emacs` or
`emacsclient` as your editor.

Activating simple-wiki-mode for these pages: This usually exploits
some naming convention for the browser's temporary files.  Here is an
example for w3m:

```
(require 'really-simple-wiki)
(add-to-list 'auto-mode-alist '("w3mtmp" . really-simple-wiki-mode))
```

## Tags

Use the following code to have `C-c C-t` insert tags.

```
(autoload 'sgml-tag "sgml-mode" t)
(define-key really-simple-wiki-mode-map (kbd "C-c C-t") 'sgml-tag)
```

If you are using another XML or SGML mode, beware of name conflicts
and help fix the situation.

## Filling

This is what I often use:

```
(add-hook 'really-simple-wiki-mode-hook 'turn-on-auto-fill)
```
