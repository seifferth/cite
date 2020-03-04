# Cite

`cite` is a [fzf](https://github.com/junegunn/fzf)-based
citekey-fuzzyfinder for use in a pandoc-markdown / plain-biblatex
workflow. The command will search the current working directory and
all subdirectories (both real and symlinked) for filenames ending
in `.bib`. From all those files (expected to be biblatex files)
a list of citekeys will be extracted and passed to fzf on stdin for
interactive selection. Selecting multiple keys is possible by marking
them by pressing Tab before hitting Enter. All arguments to `cite` are
interpreted as a single initial query. If only one citekey matches this
query, interactive selection will be skipped and the matching citekey
will be output directly.

**Note:** This branch contains a slightly extended version of the
original `cite`-command that includes functionality for handling
[jotter](https://github.com/seifferth/jotter) citekeys. If invoked
outside a `jotter`, cite will exhibit the original behaviour.

## Installation

Simply save `cite` in some directory included in your `PATH`, mark it
as executable and make sure all dependencies are satisfied.

## Dependencies

- [fd](https://github.com/sharkdp/fd)
- [fzf](https://github.com/junegunn/fzf)

## Usage

`cite` is used most efficiently when combined with a text editor. I
personally use it with [vis](https://github.com/martanne/vis), using a
[custom plugin](https://github.com/seifferth/vis-super-shellout) to
insert the output of arbitrary shell commands, but use with different
(command-line-oriented) text editors should be possible as well.

## Known Issues

- Whitespace in filenames is not supported.
- Large numbers of subdirectories seem to introduce notable latency. Large
  numbers of citekeys, on the other hand, are handled very well.
