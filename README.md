# LaTeX-letter
A LaTeX letter template that uses the `scrlttr2` class of the popular [KOMA-Script](https://www.komascript.de/).

## Example
To get an impression of the letter's design and layout please see the picture below or take a look at the [`example.pdf`](./_example/example.pdf).

![LaTeX-letter example](./_example/example.png)


## Usage
The letter template basically consists of four user-relevant files:

| file                  | description                                                                                                               |
| ----                  | -----------                                                                                                               |
| `main.tex`            | This is the main file containing basic settings, package usages and references to macros.                                 |
| `sender.lco`          | The sender information are stored in this separate file for reasons of modularity.                                        |
| `content.tex`         | The actual content of the `TeX` document is stored in this separate file for reasons of modularity.                       |
| `helpers/macros.tex`  | This file comprises typographic and layout customization as well as macros for the header, footer and location fields.    |

### General Note
Due to the barcode functionality, which makes use of the package `pst-barcode` and thus on the underlying package `pstricks`, the `.tex` files should be compiled with `xelatex`.

Please refer to the [KOMA guide](https://www.ctan.org/pkg/scrlttr2) for a comprehensive description of the KOMA variables used.


### `main.tex`
The sender information are included via the `\LoadLetterOption{}` command which loads an `.lco` file. To do so, you must specify the file name of the `.lco` file without suffix as command parameter.


### `sender.lco`
This is the file where the sender information are stored. Most (or all) standard sender attributes for the `scrlttr2` class should be stated in there; so it's pretty straightforward to fill in the blanks (or better to say: to modify the already defined variables).


### `content.tex`
In this file the specific content of the `TeX` document is stored. It contains one `letter` environment for each letter.


### `helpers/macros.tex`
As mentioned before, this file applies specific typographic and layout customization to the letter template. Usually, there is no necessity to modify this file. However, if one wants to adjust these basic settings, this is the place to do so.


## Acknowledgments
* Thanks to Markus Kohm for his great [KOMA-Script](https://www.komascript.de/) classes for LaTeX.
* Thanks to [Enrico Gregorio](https://github.com/eg9) for the [UUID v4 generator snippet](https://tex.stackexchange.com/questions/332329/how-can-one-create-a-random-guid).