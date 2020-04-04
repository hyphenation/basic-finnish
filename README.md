# Basic Finnish Hyphenation

Patterns for a basic hyphenation style of Finnish.

Work in progress, hence little documentation so far.  Below is a quick guide.

## Installation

From the top-level directory, run

    pip3 install -r requirements.txt
    python3 src/makelist

The script downloads a [XML Finnish word list](http://kaino.kotus.fi/sanat/nykysuomi/) if needed, generates [the patterns](tex/hyph-fi-x-basic.pat.txt) and hyphenates the word list with it, generating [a hyphenated list](list/hyphenated.txt).

## Test with TeX

In the [tex](`tex`) directory, compile `test-basic-patterns.tex` with LuaLaTeX.

[MIT licence](https://opensource.org/licenses/MIT)
