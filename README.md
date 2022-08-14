---
title: "Read me"
subtitle: ""
author: Till Grallert
date: 2022-06-16 
ORCID: orcid.org/0000-0002-5739-8094
---

# to do
## CMS

- [x] publication dates for journal articles: year only
- [ ] books with similar short titles and no author are not differentiated upon subsequent mentions
    + e.g. Sālnāmes
    + [x] with "NN." for anonymous authors, this has improved a bit
        * [x] add NN. for subsequent references
- [ ] translated titles
    + due to a shortcoming in the current version of CSL/ citeproc, the field `translated-title` in Zotero's extra field cannot be addressed. As a work-around people use `original-title` instead.
    + [x] remove the value from display for books
- [ ] diary entries/ manuscripts
    + works well for actual archival diaries but not printed ones, which might require XSLT transformation before import into Zotero

- [x] ad library for photos (`graphic`)
- [x] URLs and date accessed: the date should not depend on any additional condition
- [x] short titles for magazine articles:
    + due to my idosyncratic way of recording periodicals in Sente, I had originally intended for the short title of periodicals to be used as the actual publication title
    + [x] remove short title as publication title for magazine articles
- [x] missing author: should become "NN." in styles that do call for an author 
- [x] page range for magazine articles in text.
- [x] **page range for book chapters** in the bibliography
    + they come immediatly after the title and volume information. this is wrong
    + this is a **bug in the original** CSL
- [x] adopt the stable citation styles from my MLA version
- [x] stable citation for artworks / `graphic` 
    + [x] added a fallback function to generate stable ciations for any reference type

# notes
## stable citations
### MLA

```xml
<citation>
	...
	<else-if match="any" type="article-newspaper">
        <text macro="citation-newspaper"/>
        <text macro="point-locators"/>
    </else-if>
    <else-if match="any" type="personal_communication document">
        <text macro="citation-archival"/>
    </else-if>
    ...
</citation>
```

```xml
<!-- static citations -->
<macro name="citation-newspaper">
    <group delimiter=", ">
        <!-- periodical title -->
        <text macro="container-title-note"/>
        <!-- issue, volume etc. -->
        <text macro="locators-note"/>
        <!-- date -->
        <text macro="issued"/>
    </group>
</macro>
<macro name="citation-archival">
    <group delimiter=", ">
        <text macro="archive-note-largest-to-smallest"/>
        <choose>
            <if match="all" variable="publisher-place issue">
                <group delimiter=" ">
                    <text variable="publisher-place"/>
                    <text variable="issue"/>
                </group>
            </if>
            <else-if match="all" variable="publisher-place collection-title collection-number">
                <group delimiter=" ">
                    <text variable="publisher-place"/>
                    <text variable="collection-title"/>
                    <text variable="collection-number"/>
                </group>
            </else-if>
        </choose>
        <text variable="genre"/>
        <!-- problem: undocumented (?) behaviour that in sequences of multiple references with the same author-recipient combination, this is only present in the first reference -->
        <text macro="contributors-note"/>
        <choose>
            <if match="all" variable="publisher-place issue"/>
            <else>
                <text macro="title-note"/>
            </else>
        </choose>
        <text macro="issued-note"/>
    </group>
</macro>
```

## CMS

```xml
<!-- macros for stable, i.e. context-independent citations -->
<macro name="citation-stable">
    <choose>
        <if type="article-newspaper">
            <text macro="citation-newspapers"/>
        </if>
        <else-if match="any" type="letter personal_communication">
            <text macro="citation-letters"/>
        </else-if>
    </choose>
</macro>
<!-- newspapers -->
<macro name="citation-newspapers">
    <group delimiter=", ">
        <text macro="container-title-note"/>
        <text macro="locators-note-join-with-comma"/>
        <text macro="issue-note-join-with-comma"/>
    </group>
</macro>
<!-- letters -->
<macro name="citation-letters">
    <group delimiter=" ">
        <group delimiter=", ">
            <text macro="archive-note-largest-to-smallest"/>
            <text macro="contributors-note"/>
            <text macro="title-note"/>
            <!--                <text macro="issue-map-graphic"/>-->
        </group>
        <!--            <text macro="issue-note-join-with-space"/>-->
        <text macro="issue-note"/>
    </group>
</macro>
```