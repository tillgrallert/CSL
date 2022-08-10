---
title: "Citeproc bug"
subtitle: ""
author: Till Grallert
date: 2022-08-06 
ORCID: orcid.org/0000-0002-5739-8094
bibliography: ../assets/bibliography/reference.csl.json
lang: en-GB
---

# Description

Using references in notes without the surrounding angular brackets, i.e. `[^fn]: @citationKey`, the author name is moved to the beginning of the formatted citation. Example: instead of "PRO, FO 195/1514, Damascus 33, **W. Kirby Green** to Elliot" we get "**W. Kirby Green**, PRO, FO 195/1514, Damascus 33, to Elliot". When surrounded with angular brackets, this bug does not occur, i.e. `[^fn]: [@citationKey]` or `[@citationKey]`.

This seems to be the somewhat intended behaviour of **citeproc** as in "author-date" formats, the notation `@citationKey` will return `author (date)`, while `[@citationKey]` returns `(author date)`. I suspect that nobody thought of formats that would not put the author name up front even though this is the established practice in the field of history despite CMS et al. making different recommendations, e.g. "location in the archive, bibliographic description"


# Test text to be converted with Pandoc and Citeproc
## Initial reference

Morbi leo risus, porta ac consectetur ac, vestibulum at eros.[^1]

[^1]: @Dickson+1875d; @Green+1873

## References in brackets

Praesent consectetur pellentesque nibh adipiscing quis scelerisque tincidunt sagittis, imperdiet netus enim tellus fringilla sem habitant aliquam justo, posuere feugiat nunc tortor blandit bibendum fames.[^2]

[^2]: [@Dickson+1875d; @Green+1873]

# resulting output
## Initial reference

J. Dickson [**faulty**], PRO, FO 78/2419, Damascus Consular 20, to Earl of Derby, (Damascus, 24 December 1875); W. Kirby Green [**faulty**], PRO, FO 195/1514, Damascus 33, to Elliot, (Damascus, 23 July 1873).

## References in brackets

PRO, FO 195/1514, Damascus 33, W. Kirby Green [**correct**] to Elliot, (Damascus, 23 July 1873); PRO, FO 78/2419, Damascus Consular 20, J. Dickson [**correct**] to Earl of Derby, (Damascus, 24 December 1875)

# Intended output

PRO, FO 195/1514, Damascus 33, W. Kirby Green [**correct**] to Elliot, (Damascus, 23 July 1873); PRO, FO 78/2419, Damascus Consular 20, J. Dickson [**correct**] to Earl of Derby, (Damascus, 24 December 1875)