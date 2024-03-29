# Basic Finnish Hyphenation

**Patterns for a basic hyphenation style of Finnish.**

## Rationale

The current ("old") default Finnish hyphenation in TeX is based on basic
Finnish hyphenation rules but it has also many exceptions to help
hyphenating some compound words correctly. For example, it hyphenates
"vi-deo-pro-jek-to-ri" correctly because it has special rule for "pr"
letters. By the basic rules this would be "vi-de-op-ro-jek-to-ri".
(Really correct hyphenation requires a spelling checker which knows that
there are two words "video" and "projektori".)

However, the many exceptional patterns that help with some compound
words come with side effects. For example, "paprika" has "pr" too and
the exception made for things like "video-projektori" keeps "pr"
together also in words like "papri-ka" (really: "pap-ri-ka"). Word
"housut" is not hyphenated at all because there is a pattern which
prevents hyphenating between "u" and "s" (in order to help with some
compound words). There are many similar situations and the output is
sometimes unexpected.

This project develops a new optional hyphenation variant for Finnish.
The new variant follows only the basic Finnish hyphenation rules, so it
produces all possible hyphenation points. This variant doesn't have
special rules for handling some compounds words and hyphenation is
allowed between two vowels ("kofe-iini") which is not ideal in
typography.

The use of this variant requires a bit more manual hyphenation hints
with compound words ("video\-projektori") and some other cases. The
positive side is that the output is expected because it just follows
well-known basic rules. A document author knows in advance when manual
help is needed.

## Installation

From the top-level directory, run

    pip3 install -r requirements.txt
    python3 src/makelist

The script downloads an [XML Finnish word list](http://kaino.kotus.fi/sanat/nykysuomi/) if needed, generates [the patterns](tex/hyph-fi-x-basic.pat.txt) and hyphenates the word list with it, generating [a hyphenated list](list/hyphenated.txt).

## Test with TeX

In the [`tex`](tex) directory, compile `test-basic-patterns.tex` with LuaLaTeX.

[MIT licence](https://opensource.org/licenses/MIT)
