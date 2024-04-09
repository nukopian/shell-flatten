% flatten(1) 1.0.1 | flatten a series
% Iain Campbell

## NAME
flatten - flatten a series

## SYNOPSIS
	flatten [options] [--]

    Options:
		-s, --separator string
		-f, --flattened style
		-r, --rows style
		    --csv
		    --tuple
		    --list
		    --set
		-H, --no-header
		-S, --no-separator
		-Q, --no-quotes
		-h, --help

    style:
		a string used to define the opening and closing characters that wrap
		each row of the series and the final flattened result:

			style := [opening][quote]
			opening := "(" | "[" | "{"
			quote := "'" | "\""

## DESCRIPTION
Use the `flatten` filter to convert multiple rows into a single row. Input is taken from `stdin`, while output is written to `stdout`.

The `flatten` filter may also be used in conjunction with the `series` filter to reshape data into a single-line sequence. 

### Options

#### `-s`, `--separator` _string_ | `SPACE` | `NONE`

Define how to separate each element of the flattened row.

#### `-f`, `--flattened` _style_ | `NONE`

Define how to decorate the final flattened row.

#### `-r`, `--rows` _style_ | `NONE`

Define how to decorate each row prior to flattening.

#### `--csv`

A more compact alternative to `-s "," -v '""'` for a CSV list.

#### `--tuple`

A more compact alternative to `-s ',' -v "''" -f '()'` for a Python tuple-style, or SQL value-set.

#### `--list`

A more compact alternative to `-s ',' -v "''" -f '[]'` for a Python list-style.

#### `--set`

A more compact alternative to `-s ',' -v "''" -f '{}'` for a Python set-style.

#### `-H`, `--no-header`

Do not process the first row of the source table, or include it in the output series.

#### `-S`, `--no-separator`

The shorthand options specify a separator. You may use this option afterwards to cancel that effect.

#### `-Q`, `--no-quotes`

The shorthand options specify a quoting style. You may use this option afterwards to cancel that effect.

#### `-h`, `--help`

Display usage notes.
