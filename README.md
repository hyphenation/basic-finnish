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
together also in words like "papri-ka" (really: "pap-ri-ka"). There are
many similar situations. For example, word "housut" is not hyphenated at
all because there is a pattern which prevents hyphenating between "u"
and "s" (to help with some compound words). The output is sometimes
unexpected.

This project develops a new optional hyphenation variant for Finnish.
The new variant follows only the basic Finnish hyphenation rules and
doesn't try to handle compounds words. The use of this variant requires
a bit more manual hyphenation hints with compound words
("video\-projektori"). The positive side is that the output is expected
because it just follows the basic rules. A text author knows in advance
when manual help is needed. This basic hyphenation variant also gives
more possible hyphenation points.

Currently this new variant is a work in progress. It's not integrated to
(La)TeX packages or distributions.

## Installation

From the top-level directory, run

    pip3 install -r requirements.txt
    python3 src/makelist

The script downloads an [XML Finnish word list](http://kaino.kotus.fi/sanat/nykysuomi/) if needed, generates [the patterns](tex/hyph-fi-x-basic.pat.txt) and hyphenates the word list with it, generating [a hyphenated list](list/hyphenated.txt).

## Test with TeX

In the [`tex`](tex) directory, compile `test-basic-patterns.tex` with LuaLaTeX.

[MIT licence](https://opensource.org/licenses/MIT)
