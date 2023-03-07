---
title: "Pandoc reference"
subtitle: "Test formatting"
author: Till Grallert
date: 2020-09-04
ORCID: orcid.org/0000-0002-5739-8094
abstract: "Lorem ipsum dolor sit amet consectetur adipiscing, elit torquent litora dis proin eleifend, ultrices hac aptent vulputate himenaeos. Taciti massa posuere senectus cubilia per mauris lorem ad, ullamcorper purus non arcu cursus rhoncus torquent conubia, urna orci mi sapien montes libero varius. Lobortis dui primis nisi nostra netus tincidunt leo imperdiet donec ad, sem proin cursus tortor curae consectetur egestas pellentesque."
bibliography: assets/bibliography/reference.csl.json
# csl: ../csl/chicago-fullnote-bibliography_msca.csl
lang: en-US 
# for formatting with citeproc/csl one needs to use en-GB to get titles surrounded by double quotes and double quotes in titles to be converted to single quotes 
# lang: de
suppress-bibliography: false
reference-section-title: "Bibliography"
---

<!-- This file makes use of multimarkdown, pandoc, pandoc-crossref and pandoc-citeproc -->
<!-- pandoc -F pandoc-crossref -F pandoc-citeproc reference.md -o reference.html -->
<!-- pandoc -F pandoc-citeproc reference.md -o reference.html -->
<!-- pandoc --filter=pandoc-crossref --filter=pandoc-citeproc --csl=/BachUni/BachBibliothek/CSL/geschichte-und-gesellschaft.csl reference.md -o reference_processed.md -->
<!-- the bibliography is part of my AcademicWriting Zotero library -->

This file is a sample of common features in my texts to generate pandoc templates. It uses an automatically updated bibliography (Zotero -> BetterBibTeX ->CSL JSON).

# First level

## Reference types
### legal texts

Citing legal texts is a bit of a pickle. Zotero has three relevant item types, `Bill` and `Statute` but neither is really fitting to the 19th century Ottoman Empire.[^4] The Zotero item type `statute` is mapped to CSL type `legislation`, while `bill` is `bill`.

- Bill: A proposed piece of legislation
- Statute: A law or other piece of enacted legislation
    + available fields
        * name of act: title
        * Code: the name/ title of a code in which the statute was published
        * Date Enacted: mapped to the publication date

In terms of results---as opposed to purity of code and quality of bibliographic data---I recommend not using `Bill` or `Statute` but focus on the way legislation was actually published, i.e. as part of a book in a series, as newspaper article, magazine article etc. Note that due to my preference to very short references to newspapers, legislation is only somewhat correctly cited when designated as `magazine article`. The CSL style needs to support `original-date`.


### Diary entries

Diary entries are currently recorded as `manuscript`s in Zotero.[^5] This works well and makes sense for unpublished, archival journals and diaries. Published diaries could just be categorised as book chapters. 

- manuscript
- book chapter: make sure to use the following fields
    + `genre`: with the value "Journal entry"
    + `original-date`: for date of the original journal entry
    + `original-published-place`: for the location of the entry

### Letters

Letters are recorded as `letter`s in Zotero.[^11] There is, however, a problem with subsequent references by the same author within a reference group in styles that omit the author name for subsequent references (set through `@collapse` on `<cs:citation>`. The names of the author AND the **recipient** of the subsequent letters are omitted even if the latter differ. As can be deduced from this [@Dickson1885TestLetter] and this [@Dickson1885TestLettera] letter. If quoted in the same group [@Dickson1885TestLetter; @Dickson1885TestLettera], one recipient is omitted (depending on the sort order of the style).

## Other behaviours
### subsequent references by the same author

The behaviour for subsequent references by the same author in citations is set through a list of controlled values for the `@collapse` attribute on `<citation>` [@Marino2018ReadingCultureCode; @Marino+2016]. The behaviour is documented in <https://github.com/citation-style-language/schema/blob/master/schemas/styles/csl.rnc>.

- `year`
- `citation-number`
- `year-suffix`
- `year-suffix-ranged`

NOTE: `@collapse` will remove all types of contributors, including recipients, if the first author is the same and even if all other contributors differ.

## Second level

Donec sed odio dui [Books: @AbouHodeib+2017; @AlBuḥayrī+1902; @AlQasimi+1960b; @SchatkowskiSchilcher+1985, 67; @VonKremer+1853, 81-83; @Syria+salname+1878; @Syria+Salname+1879]. Donec **ullamcorper** nulla non metus auctor fringilla. Cras justo odio, dapibus ac facilisis in, egestas eget quam [Book chapters: @Danielson2021WomenVoices; @Grallert+2019; @Hanna2016TheatreMaking; @Homberg2022ElektronischerKolonialismus; @Winckler2022Seriality, 135-137 write something]. Praesent commodo cursus magna, vel `scelerisque nisl consectetur` et.[^3] Nulla vitae elit libero, a pharetra augue [Journal articles: @AbūShanab+1978; @Boyar+2006, 56-59; @Karachouli+1992; @Salzmann+1993, 78].

>Lorem ipsum dolor sit amet consectetur adipiscing elit pharetra, elementum lacus suscipit inceptos facilisis ridiculus fusce quam per, himenaeos phasellus sociis urna torquent vivamus platea. Arcu adipiscing ante nascetur dui nisl scelerisque torquent, sem ultrices metus integer eu fames maecenas senectus, cubilia ullamcorper taciti phasellus suspendisse imperdiet.[^2]

## Second level

Curabitur blandit tempus porttitor (`WP1`) [Software: @OpenArabicPE:journal_al-ustadh; @OpenArabicPE:journal_lughat-al-arab]. Cras mattis consectetur purus sit amet fermentum [Theses: @Sajdi+2002; @Weber+2006, 67-71, 99]. Integer posuere erat a ante venenatis dapibus posuere velit aliquet. Curabitur blandit tempus porttitor. Morbi leo risus, porta ac consectetur ac, vestibulum at eros. [^11]

![A test image[^1]](assets/images/example.png){#fig:img0096 width=600}

Morbi leo risus, [porta ac consectetur](abc) ac, vestibulum at eros. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Etiam porta sem malesuada magna mollis euismod. Aenean lacinia bibendum nulla sed consectetur (@tbl:t_1). Nulla vitae elit libero, a pharetra augue. Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum.


|        Donec        |    ullamcorper nulla     |                                                          non metus auctor fringilla                                                         |
|---------------------|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| Cras justo odio,    | dapibus ac facilisis in, | egestas eget quam. Praesent commodo cursus magna, vel scelerisque nisl consectetur et.                                                      |
| Duis mollis,        | est non commodo luctus,  | nisi erat porttitor ligula, eget lacinia odio sem nec elit. Aenean eu leo quam.                                                             |
| Pellentesque ornare |                          | venenatis vestibulum. Nullam quis risus eget urna mollis ornare vel eu leo. Maecenas sed diam eget risus varius blandit sit amet non magna. |

:Table caption {#tbl:t_1}

### Third level

Donec sed odio dui. Vestibulum id ligula porta felis euismod semper. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Cras mattis consectetur purus sit amet fermentum.

# Subsequent references

Donec sed odio dui [Books: @AbouHodeib+2017; @AlBuḥayrī+1902; @AlQasimi+1960b; @SchatkowskiSchilcher+1985, 67; @VonKremer+1853, 81-83; @Syria+salname+1878; @Syria+Salname+1879]. Donec **ullamcorper** nulla non metus auctor fringilla. Cras justo odio, dapibus ac facilisis in, egestas eget quam [Book chapters: @Danielson2021WomenVoices; @Grallert+2019; @Hanna2016TheatreMaking; @Homberg2022ElektronischerKolonialismus; @Winckler2022Seriality, 135-137 write something]. Praesent commodo cursus magna, vel `scelerisque nisl consectetur` et.[^3] Nulla vitae elit libero, a pharetra augue [Journal articles: @AbūShanab+1978; @Boyar+2006; @Karachouli+1992; @Salzmann+1993, 78]

>Lorem ipsum dolor sit amet consectetur adipiscing elit pharetra, elementum lacus suscipit inceptos facilisis ridiculus fusce quam per, himenaeos phasellus sociis urna torquent vivamus platea. Arcu adipiscing ante nascetur dui nisl scelerisque torquent, sem ultrices metus integer eu fames maecenas senectus, cubilia ullamcorper taciti phasellus suspendisse imperdiet.[^2]

## Second level

Curabitur blandit tempus porttitor (`WP1`) [Software: @OpenArabicPE:journal_al-ustadh; @OpenArabicPE:journal_lughat-al-arab]. Cras mattis consectetur purus sit amet fermentum [Theses: @Sajdi+2002; @Weber+2006, 67-71, 99]. Integer posuere erat a ante venenatis dapibus posuere velit aliquet. Curabitur blandit tempus porttitor.[^5] Morbi leo risus, porta ac consectetur ac, vestibulum at eros. [^11]

Morbi leo risus, [porta ac consectetur](abc) ac, vestibulum at eros. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Etiam porta sem malesuada magna mollis euismod. Aenean lacinia bibendum nulla sed consectetur (@tbl:t_1). Nulla vitae elit libero, a pharetra augue. Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum.

# forms of references

Lorem ipsum dolor [@Yıldız+2008] sit amet consectetur adipiscing[^6] elit penatibus[^7] viverra[^8] pulvinar[^9] porttitor, leo dui parturient suspendisse convallis tortor dapibus curae ut sapien [@Qasem+2015, 9; @AhmedBioud+1969]. Penatibus aenean tristique risus ac praesent vulputate inceptos laoreet nec habitant, pulvinar dui malesuada nulla velit molestie leo pharetra semper. Interdum at quis cursus scelerisque arcu diam nibh potenti porttitor, odio per et posuere varius fusce ullamcorper quam, gravida pellentesque lacus pharetra turpis felis praesent id [@Grallert+2020].

[^6]: No trailing punctuation: For xyz see @Saliba+1971 [5]
[^7]: Trailing punctuation as per `@suffix` on `cs:citation`: See @Saliba+1971 [7] on xyz.
[^8]: No trailing punctuation as per `@suffix` on `cs:citation` book sections: Compare @Seikaly+1981 [38] on abc.
[^9]: No trailing punctuation: For abc see [@Roded+1984, 3], who says bla.


[^1]: This photograph seems to show large groups of women sitting along the banks of the river at Ṣūfāniyya east of Bāb Tūmā; @UnderwoodUnderwood+1900a; @Damascus; @DamaskusJahrmarktKarussell+1917.
[^2]: Newspaper articles: [@bashir+410; @jann+1368; @lisan+70; @thamarat+272a, 1-2].
[^3]: Magazine articles: [@Butchart+1892a; @Johnston+1899; @oclc_644997575-i_17-div_8.d1e1603_en; @oclc_644997575-i_18-div_7.d2e1421_en, 23; @BulletinDeLallianceIsraélite+1892b].
[^4]: [Bills, legal texts:  @MatbuatNizamnamesi1864, §6; @MatbuatNizamnamesi1872; @NizamAlMatbuatArt171909; @NizamAlMatbuatArt171909a, §6; @Nawfal+1883e, §6-9; @Young+1905e].
[^5]: [Manuscripts incl. diary entries: @Bauernfeind+1889a; @Dickson+1882bt]
[^11]: Letters: @Dickson1885TestLetter; @Dickson1885TestLettera; @Green+1873; @Mishāqa+1900d; @Robeson+1884