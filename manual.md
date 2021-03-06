---
layout: page
title: "Manual"
description: ""
group: navigation
---
{% include JB/setup %}

Typing `bustools` produces a list of usage options, which are:

To see a list of available commands type `bustools` in the terminal

~~~
> bustools 
Usage: bustools <CMD> [arguments] ..

Where <CMD> can be one of:

sort            Sort bus file by barcodes and UMI
text            Output as tab separated text file

Running bustools <CMD> without arguments prints usage information for <CMD>
~~~

### Sorting

Raw BUS output from pseudoalignment programs may be unsorted. To simply and accelerate downstream processing BUS files can be sorted using `bustools sort`

~~~
> bustools sort 
Usage: bustools sort [options] bus-files

Options:
-t, --threads         Number of threads to use
-o, --output          File for sorted output
~~~

This will create a new BUS file where the BUS records are sorted by barcode first, UMI second, and equivalence class third.

### Text

BUS files can be converted to a tab-separated format for easy inspection and processing using shell scripts or high level languages. `bustools text` 

~~~
> bustools text
Usage: bustools text [options] bus-files

Options: 
-o, --output          File for text output
~~~

### Capture

`bulstools capture` can separate BUS files into multiple files according to some criteria 

~~~
Usage: bulstools capture [arguments] ouput-directories

Required arguments:
-i, --classes=STRING          Filename with equivalence classes to be split to
-o, --output-dir=STRING       Directory to write output to
~~~

### Inspect

`bustools inspect inspect` outputs quality control metrics of the BUS file provided
~~~

Usage: bustools inspect BUS-file

~~~

### version

`bustools version` displays the current version of the software.
