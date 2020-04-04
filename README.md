# Basic Finnish Hyphenation

Patterns for a basic hyphenation style of Finnish.

Work in progress.  Installation instructions:

    pip3 install -r requirements.txt
    python3 src/makelist

The script downloads a [XML Finnish word list](http://kaino.kotus.fi/sanat/nykysuomi/) if needed, generates [the patterns](src/hyph-fi-x-basic.pat.txt) and hyphenates the word list with it, generating [a hyphenated list](list/hyphenated.txt).

[MIT licence](https://opensource.org/licenses/MIT)
