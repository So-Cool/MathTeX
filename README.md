# MathTeX #

> Generate LaTeX equations on MacOS directly in terminal.
> Supports I/O stream, clipboard and file; pdf, png and svg.

```
MathTeX 0.1 - Render LaTeX Mathematics
Copyright Kacper Sokol <dev@kcpr.me>

By default MathTeX tries to read equation from stream (piped data);
if this fails, it attempts to load the contents of the clipboard.
The equation can also be specified explicitly by using the -e flag,
read from STDIN by providing the -x flag,
or given in a source file.

The output is sent to clipboard by default;
using the -c flag switches it to STDOUT.
Alternatively, a file can be given with the -o flag.

Options
  -e <equation>     LaTeX mathematics
  -x                Input from STDIN
  -o <file>         Output to file
  -t <format>       Format of the output file (pdf, png, svg)
  -c                Output to STDOUT

  -m <env>          Math environment
  -s <size>         Fontsize
  -d <dpi>          Output resolution in dpi
  -b <colour>       Background colour ('none' for transparent)
  -f <colour>       Foreground colour

  -p <packages>     Colon-separated list of LaTeX package names
  -i <file>         Insert contents of file into preamble

  -l <file>         Log filename
  -q                Do not print output filename (quiet mode)

  -h                Print this help message
  -v                Display version

Usage
  cat equation.tex | mathtex -c | imgcat          # stream to stream
  mathtex -b transparent                          # clipboard to clipboard
  mathtex -s 12 -x                                # STDIN to clipboard
  mathtex -p amssymb:amsmath -e "A \triangleq B"  # flag to clipboard
  mathtex -o equation.pdf -e "E=mc^2"             # flag to file
  mathtex -c equation.tex                         # file to clipboard
```

---

This programme was inspired by [LaTeXiT][latexit], and
draws heavily from [pnglatex][pnglatex].

## TODO ##

- [ ] Consider implementing options available in many of the online generators
      (border; margin; padding; mode: inline|compressed;
      font face: latin modern|verdana|computer modern|helvetica;
      font size: tiny|small|normal|large|very large|huge).
- [ ] Publish on `brew`

[latexit]: https://www.chachatelier.fr/latexit/
[pnglatex]: https://github.com/mneri/pnglatex
