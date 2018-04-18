[![](https://travis-ci.org/ashang/sdcv.svg?branch=master)](https://travis-ci.org/ashang/sdcv)

[![](https://img.shields.io/badge/license-GPL%202-brightgreen.svg)](https://github.com/ashang/sdcv/blob/master/LICENSE)

# How to compile and install

``` bash
mkdir /tmp/build-sdcv
cd /tmp/build-sdcv
cmake path/to/source/code/of/sdcv
make
```

If enabled nls

``` bash
make lang
```

## To install

``` bash
make install
```

You can use "DESTDIR" variable to change installation path.

# Documentation

See sdcv man page for usage description.

# Bugs

If you find bugs report it via email to dushistov at mail dot ru. Be
sure to include the word "sdcv" somewhere in the "Subject:" field.

# Notes to developer

## make source code release

``` bash
make package_source
```

## update translation

``` bash
cd po
xgettext -k_ ../src/*.cpp -o new.pot
msgmerge -U sdcv.pot new.pot
rm new.pot
for i in `ls *.po`; do msgmerge -U $i sdcv.pot; done
```
