CSV5
====

Reverse engeneering of existing CSV files out there


The plan is to describe how to parse a CSV based on reverse engeneering it, à la HTML5

We should describe a state machine that could parse a CSV and create a memory representation of it

This memory representation could then be translated into [CSV+](http://w3c.github.io/csvw/syntax/)

It should describe what CSVLint is doing in a more step by step basis

# Algorithm

## Character Encoding Detection And Convertion from Bytes to Text

BOM ?

* UTF-8
* ISO-8859-1
* etc.

See http://www.whatwg.org/specs/web-apps/current-work/multipage/parsing.html#the-input-byte-stream

## Parsing State Algorithm

A la http://www.whatwg.org/specs/web-apps/current-work/multipage/parsing.html#parse-state

### Tokenisation 
A la http://www.whatwg.org/specs/web-apps/current-work/multipage/tokenization.html#tokenization

Note : when we start reading the first line we should be able to detect that it's a header state


header state

Data State / Cell state
Consume the next input character:
> ↪ U+0009 CHARACTER TABULATION (tab) : switch to "TABULTED state"

> ↪ U+002C COMMA : switch to "COMMA state"

> ↪ U+003B SEMICOLON : switch to "SEMICOLON state"

> ↪ U+0022 QUOTATION MARK (") : switch to "In Quotation state"

> ↪ U+0027 APOSTROPHE (') : switch to "In APostrophe state"

> ↪ EOF : switch to "close state"

> ↪ Anything else : push character in "data state"

 - 
