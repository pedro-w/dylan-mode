dylan-mode
==========

dylan-mode is a major mode for editing Dylan code in emacs.

If you've installed dylan-mode through a package manager, the mode should be
activated for `.dylan` files. Otherwise, add the following to your .emacs file::

  (add-to-list 'load-path "/path/to/dylan-mode")
  (require 'dime)


DIME/dswank
===========

DIME/dswank is part of the release since opendylan-2011.1. It
provides interactive development support in emacs. DIME is a fork of
`SLIME <http://common-lisp.net/project/slime/>`_ and stands for Dylan
Interaction Mode for Emacs.

If you did not install dylan-mode through a package manager, add the following
to your .emacs file::

  (require 'dime)

To configure DIME/dswank add these lines to your .emacs file, changing
YYYY.nn as appropriate for your installed release of Open Dylan::

  (dime-setup '(dime-browse dime-repl dime-note-tree))
  (setq dime-dylan-implementations
        '((opendylan ("/opt/opendylan-YYYY.nn/bin/dswank")
                     :env ("OPEN_DYLAN_USER_REGISTRIES=/opt/opendylan-YYYY.nn/sources/registry"))))

You will also want to add your own source registries to the
`OPEN_DYLAN_USER_REGISTRIES` environment variable. Registry paths are separated
by semicolons on Windows and colons elsewhere.


License
=======

This code is distributed under the GNU GPL.

It originates from different sources:

* dylan-mode.el is from CMU
* dylan-opt.el from Harlequin
* dylan-dime.el from Dylan Hackers
* dime.el, dime-repl.el, dime-note-tree.el from SLIME
