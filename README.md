CSV5
====

Reverse engeneering of existing CSV files out there


The plan is to describe how to parse a CSV based on reverse engeneering it, à la HTML5

We should describe a state machine that could parse a CSV and create a memory representation of it

This memory representation could then be translated into CSV+

It should describe what CSVLint is doing in a more step by step basis

Algorithm
=========

Character Encoding Detection And Convertion from Bytes to Text
============================
BOM ?

* UTF-8
* ISO-8859-1
* etc.

See http://www.whatwg.org/specs/web-apps/current-work/multipage/parsing.html#the-input-byte-stream

Parsing State Algorithm
=======================

A la http://www.whatwg.org/specs/web-apps/current-work/multipage/parsing.html#parse-state
