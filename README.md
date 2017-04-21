# setup-compile.el

## Commentary:

`setup-compile.el` provides a command that makes it easy to quickly set a
sensible compile command for the given buffer. Essentially it checks to see
if there's a Makefile in the directory and, if there isn't, it builds a
command that should do the job.

A call to `setup-compile` is generally best done in a major mode's hook.
These days I'm using it
with [`use-package`](https://github.com/jwiegley/use-package) like this:

```elisp
(use-package cc-mode
  :ensure t
  :config
  (add-hook 'c-mode-hook   #'setup-compile)
  (add-hook 'c++-mode-hook #'setup-compile)
  :bind
  (:map c-mode-map   ("RET" . newline-and-indent))
  (:map c++-mode-map ("RET" . newline-and-indent)))
```
