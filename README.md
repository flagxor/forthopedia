# Forthopedia

The Forth programming language is all about simplicity.
The core idea of the language, words defined in terms of other words,
is simplicity itself.
While the language has a range of other potent capabilities:
dual stacks, hybrid compilation and interpretation,
reflection, dynamic code generation, and more,
the key to understanding what Forth is and could be, is through its vocabulary.

To that end, this repository is meant to collect information on the origin,
evolution, history, and motivations of the words used in the many dialects of Forth.
While Forth has has a range of standards, Forth's heritage exceeds these.
For good or ill, the adage, "If you've seen one Forth, you've seen one Forth",
is accurate. Therefore we'll construe Forth broadly and include words
from these many variants.

The structure and organization of this document will need to involve as more
content is added. For the moment, it will be structured by topic.

## Listing known words

### VLIST

Forth-79 --- List  the  word names of the CONTEXT vocabulary starting with
the most recent definition.

### WORDS

Introduced in ANSForth94, to align with common practice.

Open Question: Why was VLIST not sufficient?

## Boolean and Logical Inverse 

### INVERT

Introduced in ANSForth94 to replace NOT.

### NOT

Forth-79 --- Equivalent to 0=

Forth-83 --- Equivalent to -1 XOR

ANSForth94 --- Deprecated due to confusion

## Parsing input stream

### WORD

```
WORD ( delimiter -- a )
```

Parse one word, skipping delimiter until non-delimiter and then parsing to the
next instance.

Introduced in Forth-79.

### PARSE

```
PARSE ( delimiter -- a n )
```

Introduced in ANSForth94 to avoid edge cases like:

```
: .(   [CHAR] )  WORD COUNT TYPE ;  IMMEDIATE

.( )   5 .
```

