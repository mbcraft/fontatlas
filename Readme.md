FontAtlas
==========

Install
-------

You need libfreetype6-dev installed to compile it.

```sh
$ mkdir build && cd build && cmake .. && sudo make install
```

Usage
-----

There is two binaries generated by fontatlas.

### font_data

Use this binary to generate a json which contains all the meta-data, and all the png atlas file for a given font.

```shell
$ font_data ../league.ttf
Generated ../league.ttf.1.png
Generated ../league.ttf.json
$
```

### font_meta_data

This one will generate a binary meta-data file.

```
$ font_meta_data ../league.ttf
Compute meta data....
Generated ../league.ttf.meta
$
```

After in our main program, use `osgStupeflix::FontAtlas::generateFromChar` function to generate the json and png file for a range of characters. Moreover, the function will return the index of the json and png file in which the character is stored. If the index is 2, and the font is league, the files will be:

- league.ttf.2.png
- league.ttf.2.json
