==============
art-fhicl-mode
==============

Commentary:
-----------

 This is a major mode for editing files FHiCL files that are used
 with the art framework.  It has rudimentary commenting features and
 indentation support.  The syntax highlighting is done such that
 strings reserved to/used by FHiCL or art are placed in either:

   constant-face,
   keyword-face,
   function-name-face, or
   type-face

 depending on the priority of the string (according to the author's
 understanding of FHiCL and art).  Very little attempt has been made
 to optimize the syntax below, due to the author's very limited
 knowledge of elisp.

 This mode was developed with help from Andrei Gaponenko (Fermilab).

Installation:
-------------

 The following must be added to your .emacs file:

    (load "art-fhicl-mode.el" nil t t)
    (add-to-list 'auto-mode-alist '("\\.fcl$" . art-fhicl-mode))

Known Bugs:
-----------


 (1) Strings that start in a comment take precedence.  For example,
     the following line:
    # here is comment with a "string
     could cause a problem if not terminated in a subsequent comment
     line.

 (2) For lines using multiple assignments and the modified binding
     operators (e.g.):
    here @protect_error: are   two: assignments
     The "two" name will not be highlighted correctly.
