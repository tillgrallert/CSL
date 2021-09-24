---
title: "Pandoc reference"
subtitle: "Test formatting"
author: Till Grallert
date: 2020-09-04
ORCID: orcid.org/0000-0002-5739-8094
bibliography: assets/bibliography/reference.csl.json
lang: en-GB
# lang: de
suppress-bibliography: false
notes-after-punctuation: true
reference-section-title: "Bibliography"
---

<!-- pandoc --citeproc --csl=/BachUni/BachBibliothek/CSL/chicago-fullnote-bibliography-short-title-subsequent_history.csl --to=pdf -->

## Heading 2

Lorem ipsum dolor [@Yıldız+2008] sit amet consectetur adipiscing[^2] elit penatibus[^3] viverra[^4] pulvinar[^5] porttitor, leo dui parturient suspendisse convallis tortor dapibus curae ut sapien [@Qasem+2015, 9; @AhmedBioud+1969]. Penatibus aenean tristique risus ac praesent vulputate inceptos laoreet nec habitant, pulvinar dui malesuada nulla velit molestie leo pharetra semper. Interdum at quis cursus scelerisque arcu diam nibh potenti porttitor, odio per et posuere varius fusce ullamcorper quam, gravida pellentesque lacus pharetra turpis felis praesent id [@Grallert+2020].

[^2]: No trailing punctuation: For xyz see @Saliba+1971 [5]
[^3]: Trailing punctuation as per `@suffix` on `cs:citation`: See @Saliba+1971 [7] on xyz.
[^4]: No trailing punctuation as per `@suffix` on `cs:citation` book sections: Compare @Seikaly+1981 [38] on abc.
[^5]: No trailing punctuation: For abc see [@Roded+1984, 3], who says bla.

# Heading 1
## Heading 2

Lorem ipsum dolor sit amet consectetur adipiscing ([@fig:barada]), elit eget sed curae volutpat turpis feugiat [@AhmedBioud+1969, 3-10], habitasse primis praesent tellus mollis. Sit enim ultrices sagittis eleifend tempor natoque pharetra facilisis, euismod magnis quam dis vivamus tincidunt id. Eget vehicula per habitant lacus tempor nisi natoque massa, cursus accumsan dolor pretium ac tortor urna, taciti lectus enim mi torquent cras nisl. Proin nisi mauris hendrerit ultrices ante quis velit inceptos pretium nunc, id ridiculus augue donec pharetra facilisis pulvinar platea parturient dolor, porta amet posuere dictum molestie mattis scelerisque interdum blandit. Et venenatis hendrerit ultricies imperdiet fusce porta orci, leo habitant taciti proin ipsum mi tincidunt, eu fringilla lectus praesent non per. Cum nisl mauris blandit erat urna fusce justo eget aenean et, at leo suscipit fringilla torquent nibh ut dis. Fusce ante nisl eleifend velit dolor bibendum, suscipit placerat augue tempus nunc, enim per orci eget ac. Lorem adipiscing turpis et sapien primis sodales magna in, vivamus senectus faucibus platea ligula tortor interdum.

>Lorem ipsum dolor sit amet consectetur adipiscing elit sagittis, tellus class porttitor lacinia conubia dapibus leo iaculis, at non aliquet sodales nostra sed erat. Nulla platea ut augue bibendum risus erat nibh, aliquet eros ligula torquent varius dictumst laoreet litora, convallis cubilia urna habitant vitae montes.[@Bohstedt+1983]

### Heading 3

Suscipit justo nibh ullamcorper dictum molestie conubia pulvinar euismod consectetur, ultrices ridiculus rutrum pharetra massa dignissim tincidunt pretium interdum id, vestibulum bibendum faucibus urna leo duis taciti tortor. Cum facilisis phasellus mattis cubilia etiam ligula dignissim sociis suscipit tempor primis nullam, vulputate euismod fringilla nibh tellus accumsan porta placerat fermentum tristique. Odio risus ligula turpis luctus bibendum nibh posuere taciti fermentum nisl facilisi euismod, varius non tempus commodo litora a congue curabitur ullamcorper vestibulum. Nibh fermentum sodales per interdum conubia id gravida, ut quam posuere odio viverra dis ipsum, platea lectus facilisi primis faucibus eu.

![Photo of Damascus](assets/images/img0096.jpg){#fig:barada}

Tincidunt venenatis faucibus ac dignissim convallis dictum quis quisque fringilla molestie, erat eleifend torquent dictumst aenean interdum conubia consectetur cursus feugiat, in ultrices sollicitudin bibendum pulvinar inceptos luctus leo suspendisse. Commodo feugiat ac conubia donec quis magnis ullamcorper hac, elementum viverra congue natoque condimentum quam faucibus tempus ornare, ridiculus aptent rhoncus quisque pretium netus nisi.

Et magna est tortor rhoncus ac dignissim dapibus sit per, fermentum dolor dis suspendisse vehicula sed primis auctor, nam quam netus mollis aptent erat justo urna. Porta dictumst gravida consequat praesent aptent tempus nam vitae, nostra adipiscing iaculis nulla at torquent curabitur augue sed, fames netus massa sociis sollicitudin faucibus curae. Curabitur feugiat pharetra consequat risus varius eu in habitant elementum eleifend facilisis luctus habitasse dolor lectus, fusce quisque sed ridiculus arcu suscipit mattis ipsum hendrerit condimentum vehicula himenaeos dui. Eleifend cum suscipit massa natoque facilisi iaculis est augue, tortor lectus duis orci nam vehicula facilisis dolor erat, vulputate ridiculus rhoncus per velit porta ac. Vehicula dui inceptos sagittis placerat eros mattis conubia, habitasse ad vel fusce nunc libero eu, magnis ullamcorper venenatis suspendisse nisl ut.

```xml
<div change="#d2e889" subtype="article" type="item" xml:id="div_2.d1e1319" xml:lang="ar">
    <head xml:id="head_2.d1e1321" xml:lang="ar">
        <persName change="#d2e859" ref="oape:pers:2872 viaf:54154379" xml:id="persName_8.d1e1322" xml:lang="fr-Arab-AR">
            <forename change="#d2e659 #d2e941" xml:id="forename_5.d2e1414" xml:lang="fr-Arab-AR">جول</forename>
            <surname change="#d2e659 #d2e941" xml:id="surname_5.d2e1417" xml:lang="fr-Arab-AR">سيمون</surname>
        </persName>
        <lb change="#d2e889" ed="print" edRef="#edition_1" xml:id="lb_1.d1e1325" xml:lang="ar"/>
        <num resp="#pers_TG" type="auto-markup" value="1814" xml:id="num_1.d1e708" xml:lang="ar">١٨١٤</num>—
        <num resp="#pers_TG" type="auto-markup" value="1896" xml:id="num_1.d1e711" xml:lang="ar">١٨٩٦</num></head>
</div>
```

Interdum massa ante litora pharetra posuere cubilia, leo pellentesque elementum magna ipsum mi suscipit, nullam quam volutpat dolor magnis. Potenti consectetur in natoque arcu fames rhoncus quam erat lacinia dictumst, hac non pharetra sed nisl metus maecenas elementum suspendisse mattis, posuere gravida tincidunt pretium montes magnis integer imperdiet habitant. Ante pharetra elementum parturient cras lorem porta etiam nascetur praesent sodales metus, consectetur fames quis aliquet ullamcorper cursus et purus eu. Semper arcu nascetur platea dignissim rhoncus sociis ante elit facilisi felis eleifend, sed etiam dictum sollicitudin imperdiet mauris sit blandit potenti.

