# Introduction #

The RNG To DTD converter for DITA is not fool proof and will not implement all the RNG grammar but only the subset used in the DITA 1.2 RNG implementation.

In RNG, definitions are located in a single file; in DTD, definitions are in two files and it is not always clear which definitions should go in the .ent file instead of the .mod file.


# Details #

All element and attribute lists declarations are in the .mod file.

For parameter entities, this is not clear.
Current implemented logic is:
  * by default, all parameter entities are in the .mod file
  * domain attribute declaration is in the .ent file

Notes:
  * RNG annotations:
    * at element level: converted into a comment in .mod file
    * at attribute level: ignored
  * is there a uniqueness rule for the RNG define/@name ? It seems that _domains-atts\_value_ is used several times ...