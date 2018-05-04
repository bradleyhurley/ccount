# ccount
A Python utility that will return the number of columns from standard in, text, gzip, or bzip files to standard out using magic to inspect the files MIME Type.

### Magic Dependencies

On Windows, copy magic1.dll, regex2.dll, and zlib1.dll onto your PATH from the Binaries and Dependencies zipfiles provided by the [File for Windows](http://gnuwin32.sourceforge.net/packages/file.htm) project.  You will need to copy the file `magic` out of `[binary-zip]\share\misc`, and pass it's location to `Magic(magic_file=...)`

On OSX:

- When using Homebrew: `brew install libmagic`
- When using macports: `port install file`

## Configuration
* Create virtualenv
* pip install -r requirements.txt

## Usage
> python ccount --help
```
Options:
  --input FILENAME  The file to read as input or '-'for standard in.  Default = '-'
  --delimiter TEXT  The file delimiter.  Default='|'
  --help            Show this message and exit.
```
You can also add ccount to your path to run from your terminal.

> ./ccount --help
```
Options:
  --input FILENAME  The file to read as input or '-'for standard in.  Default = '-'
  --delimiter TEXT  The file delimiter.  Default='|'
  --help            Show this message and exit.
 ``` 

## Examples

`> cat sample_file | ./ccount`

4

`> python ccount --input sample_file`

4
## Other
You could always use awk to get the same result, but I wanted to work on a simple project and use Click for command line arguments.

`> awk -F '|' '{print NF}' sample_file`

4

