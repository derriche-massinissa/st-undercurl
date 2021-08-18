<h1 align="center" style="border-bottom: none;">
	<a href="https://github.com/hexoctal/zenith">ST Undercurl</a>
</h1>
<h3 align="center">A patch for ST (Simple Terminal) adding support for curly and colored underlines.</h3>
<p align="center">
	<a href="#screenshots">Screenshots</a> |
	<a href="#installation">Installation</a>
	<a href="#style">Style</a>
</br>
</br>
<a href=""><img alt="platforms" src="https://img.shields.io/static/v1?label=Platforms&message=Linux&color=blue&style=flat-square"></a>
<a href="https://github.com/hexoctal/zenith/blob/master/LICENSE.md"><img alt="license" src="https://img.shields.io/static/v1?label=License&message=MIT&color=green&style=flat-square"></a>
</br>
<a href="https://github.com/hexoctal/st-undercurl/issues"><img alt="issues" src="https://img.shields.io/github/issues-raw/hexoctal/st-undercurl.svg?style=flat-square"/></a>
<a href=""><img alt="size" src="https://img.shields.io/github/repo-size/hexoctal/st-undercurl?style=flat-square"></a>
<a href=""><img alt="starts" src="https://img.shields.io/github/stars/hexoctal/st-undercurl?style=social"></a>
</br>
</p>

#

## Screenshots

![terminal neovim lsp](images/terminal3.png)
![terminal](images/terminal.png)
![terminal](images/terminal2.png)

## Installation

Install like any other patch. Go into the source directory of ST, and run the
following command:
```shell
patch < ../st-undercurl-0.8.4-20210424.diff
```

Then build it:
```shell
make
```

For installation, you either use Make (recommended):
```shell
make install
```
And you're done!

Or any other method, but in this case, you __HAVE__ to update the `TermInfo` database of
your system, to let terminal programs (Like Vim and such) know that ST supports
special underlines. You do this with the following command:
```shell
tic -sx st.info
```

## Style

You can choose between three different curly underline styles:

Curly:
![style curly](images/style_curly.png)

Spiky:
![style spiky](images/style_spiky.png)

Capped:
![style capped](images/style_capped.png)

To change the style, edit the `config.def.h` file, it looks like this:
```cpp
// Available styles
#define UNDERCURL_CURLY 0
#define UNDERCURL_SPIKY 1
#define UNDERCURL_CAPPED 2
// Active style
#define UNDERCURL_STYLE UNDERCURL_CAPPED
```

Just modify `UNDERCURL_STYLE` to one of the three available styles.
