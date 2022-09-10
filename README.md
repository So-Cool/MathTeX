# MathTeX #

```vimscript
function! s:SaveFileTMPMacOS(imgdir, tmpname) abort
    let tmpfile = a:imgdir . '/' . a:tmpname . '.png'
    let clip_command = 'osascript'
    let clip_command .= ' -e "set png_data to the clipboard as «class PNGf»"'
    let clip_command .= ' -e "set referenceNumber to open for access POSIX path of'
    let clip_command .= ' (POSIX file \"' . tmpfile . '\") with write permission"'
    let clip_command .= ' -e "write png_data to referenceNumber"'
```

```bash
osascript -e 'set the clipboard to POSIX file "/Users/kacper/Downloads/xxx.png"
```

This programme was inspired by [LaTeXiT][latexit] and
draws heavily from [pnglatex][pnglatex].

## TODO ##

- [ ] Look at one of the online generator and see what other parameters
      could be added (e.g., border, margin, padding)
- [ ] Publish on `brew`

[latexit]: https://www.chachatelier.fr/latexit/
[pnglatex]: https://github.com/mneri/pnglatex
