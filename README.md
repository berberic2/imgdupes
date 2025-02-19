# imgdupes
Find duplicate images

## imgdupes



imgdupes scans the directory-tree of the given directories, compares the found images and writes a list of multiples to stdout. 

``` bash
usage: imgdupes directories,…
```

There is one line per image containing the path and groups with similar images are separeted by empty lines. It ends with an empty line. Example:

    C/a.png
    b.png
    D/A/X/u.jpg

    f.jpg
    e.png

You might want to use imgdupes with tee like 
``` bash
imgdupes | tee dupes.out
```
to capture the output in a file.

## imgdupes-ui
imgdupes-ui works on Linux. It will not work on other systems.

imgdupes-ui is a Qt UI to display 

``` bash
usage: imgdupes-ui [file]
```

is meant to be startet from a terminal, because all error-messsages and warning will be written to stderr.
It allows to view duplicate images, delete them using the context-menu (right mousebutton) and export the path of an image with drag-and-drop

imagedups-ui takes either 
- zero arguments. In this case it reads the list of files from stdin or
- one argument. In this case the file must be a text-file containing 

It might be used with imgdupes in a pipe:
``` bash
imgdupes [directories] | imagedups-ui
```
