---
title: AccessibilitySummary Authoring Guidelines
...

## Status of This Document
Editors Draft - Version 0.9 (06/12/2019)

This document is published by the DIAGRAM Center Standards Working Group and DAISY's Transition to EPUB Working group as an Editor's Draft.

Comments regarding this document are welcome. Please [file an issue using our GitHub repository issue tracker](https://github.com/benetech/AccessibilitySummaryEPUBMetadata/issues).

---


## Table of Contents

- [Introduction](#introduction)
- [Before you start writing](#before-you-start-writing)
- [Some High-Level Considerations](#some-high-level-considerations)
- [What to Include in the `AccessibilitySummary`](#what-to-include-in-the-accessibilitysummary)
- [Examples](#examples)
- [Acknowledgements](#acknowledgements)

## Introduction

The [EPUB Accessibility Conformance and Discovery Specification defines a
schema.org metadata term called "accessibilitySummary."](http://www.idpf.org/epub/a11y/#sec-disc-package) 
This piece of metadata is extraordinarily unique and important in that it provides a
human readable description of the accessibility of the publication. It
is expected that people who do not have formal training in HTML, EPUB,
or who are not experts in accessibility will be reading the
accessibilitySummary. Online Library and retail catalogues should
present the accessibilitySummary to assist in making the decision to
purchase or recommend the title. Individuals, professors, schools and
universities should be basing their decisions to purchase on the
accessibility of products.

The metadata accessibilitySummary can be found in either of two places, inside the EPUB in the OPF file, or this information can be retrieved from ONIX [code list:
196](https://ns.editeur.org/onix/en/196); Code: 00:
Accessibility Summary.

---

**Note**: Please refer to the [Guidelines for discovery and presentation of
EPUB Accessibility metadata](https://benetech.github.io/UX-Guide-EPUB-A11y-Metadata/UXGuideForMetadata.html) for libraries and retailers.

---

## Before you start writing

The [Accessibility Checker for EPUB (Ace by DAISY)](https://daisy.github.io/ace/) is a tool which can be used to help you determine some of the accessibility features within the publication.  This information can be found when looking at the report.html file Ace creates. This will help you determine what should be included in the accessibilitySummary that will be put into the OPF file and/or ONIX metadata feed.

Next read the accessibility metadata in the EPUB package.opf file before
you begin to write. Make note of the features listed in the metadata as
you prepare to write. One should always truthfully represent the
accessibility of the publication and point out shortcomings of the
publication; students may be able to get assistance from their school or
university if some aspects of the publication are not accessible. For
example, if complex graphics that convey information do not have an
extended description, let people know that extended descriptions are not
available.

## Some High-Level Considerations

- Use simple language that communicates effectively to a non-technical and a non-accessibility aware community.
- Avoid terms that are only known in a specific knowledge domain, or explain the term in a simple way.
- Write out the words of the acronym before using the abbreviation, e.g. Web Content Accessibility Guidelines (WCAG).
- Include all accessibility features, even those detailed in another schema.org metadata item; remember that the AccessibilitySummary may be the only piece of metadata that some users read.
- Templates may be a useful approach for creating accessibility summaries in your organization, especially if all the content of a similar type goes through the same workflow and quality assurance process. However, make sure that the `accessibilitySummary` metadata that ships with the publication is accurate and applies to this particular publication.

## What to Include in the `AccessibilitySummary`

> Madeleine: Reformat as a table with 2 columns: metadata text and
suggested prose for summary. Third column for links to explanatory
notes?

Here is a list of areas that the summary should address :

### Accessibility Conformance Statement
| Metadata Value(s) Present | Suggested summary | Information |
| --------------- |-------------------|------------------------------|
| *conformsTo* = *'http://www.idpf.org/epub/a11y/accessibility-20170105.html#wcag-a'*| This publication meets accepted accessibility guidelines (WCAG-A)|WCAG-A Compliance|
| *conformsTo* = *'http://www.idpf.org/epub/a11y/accessibility-20170105.html#wcag-aa'*| This publication meets accepted accessibility guidelines (WCAG-AA)|WCAG-AA Compliance|

### Screen Reader Friendly
| Metadata Value(s) Present | Suggested summary | Information |
| --------------- |-------------------|------------------------------|
| *accessModeSufficient* = *'textual'* and *conformsTo* of *WCAG-A* or greater| This title is screen reader friendly and it will be accessible to a person using text-to-speech or refreshable braille. |Can this EPUB be entirely read by a Screen Reader, i.e. all visual only information has a meaningful text equivalent.|

### Audio Book
| Metadata Value(s) Present | Suggested summary | Information |
| --------------- |-------------------|------------------------------|
| *accessModeSufficient* = *'auditory'*|||
| *accessModeSufficient* = *'auditory'* and *accessModeSufficient* = *'textual'|||

### Accessibility Features
| Metadata Value(s) Present | Suggested summary | Information |
| --------------- |-------------------|------------------------------|
|*accessibilityFeature* = *'alternativeText'*|||
|*accessibilityFeature* = *'annotations'*|||
|*accessibilityFeature* = *'audioDescription'*|Video has Descriptive Audio||
|*accessibilityFeature* = *'bookmarks'*|||
|*accessibilityFeature* = *'braille'*|||
|*accessibilityFeature* = *'captions'*|Video has text Captions||
|*accessibilityFeature* = *'ChemML'*|||
|*accessibilityFeature* = *'describedMath'*|||
|*accessibilityFeature* = *'displayTransformability'*|||
|*accessibilityFeature* = *'highContrastAudio'*|||
|*accessibilityFeature* = *'highContrastDisplay'*|||
|*accessibilityFeature* = *'index'*|||
|*accessibilityFeature* = *'largePrint'*|||
|*accessibilityFeature* = *'latex'*|||
|*accessibilityFeature* = *'longDescription'*|Extended descriptions are provided for complex graphical content that conveys important information for understanding of the content.|Extended descriptions: Extended (or long) descriptions are used when complex graphics or other highly visual components convey information. The extended description communicates the equivalent information through text, tables, etc.|
|*accessibilityFeature* of *'longDescription'* is missing|This publication contains graphical content that conveys significant information. This graphical material is not explained and the reader who cannot interpret the graphics should seek assistance.|Extended Descriptions are not provided when needed, for example if there is a complex image that needs a longer description to understand what the image is protraying.|
|*accessibilityFeature* = *'MathML'*|Math represented by MathML||
|*accessibilityFeature* = *'none'*|@@ - Include this? I don't see how this could be possible.||
|*accessibilityFeature* = *'printPageNumbers'* and *dc:source* is present|Page numbers are present and navigation to pages is supported.|Page navigation provided and matches the print book|
|*accessibilityFeature* = *'printPageNumbers'* and *dc:source* is not present or refers to this EPUB|There is no print version of this publication, but digital page numbers are provided for ease of use.|Page navigation provided but no equivalent print book.  Since there is no print equivalent book these page breaks are set by the publisher to aid in navigating to a specific digital or "virtual" page within the EPUB.|
|*accessibilityFeature* of *'printPageNumbers'* is missing|This publication does not contain page numbers that can be navigated.|No page navigation provided|
|*accessibilityFeature* = *'readingOrder'*|||
|*accessibilityFeature* = *'rubyAnnotations'*|||
|*accessibilityFeature* = *'signLanguage'*|||
|*accessibilityFeature* = *'structuralNavigation'* and *'tableOfContents'*|This publication contains a  table of contents for navigation through the various chapters and sections.|Table of Content Navigation|
|*accessibilityFeature* = *'synchronizedAudioText'*|||
|*accessibilityFeature* = *'tactileGraphic'*|||
|*accessibilityFeature* = *'tactileObject'*|||
|*accessibilityFeature* = *'timingControl'*|||
|*accessibilityFeature* = *'transcript'*|||
|*accessibilityFeature* = *'ttsMarkup'*|||
|*accessibilityFeature* = *'unlocked'*|@@ - Include this? This may not be under Publisher control||

### Accessibility Hazards
Accessibility hazards: Some content, especially videos, may contain elements that have been found to be problematic. Most common items are motion effects that make some people motion sick, flashing that can cause severe distractions or even seizures, or loud sharp noises like a gunshot which can cause hearing issues. It is only necessary to include this information if it is present.

| Metadata Value(s) Present | Suggested summary | Information |
| --------------- |-------------------|------------------------------|
|*accessibilityHazard* = *'flashing'*|Caution: the video contains flashing lights.|Flashing Hazard|
|*accessibilityHazard* = *'sound'*|Caution: the audio contains loud noises.|Sound Hazard|
|*accessibilityHazard* = *'motionSimulation'*|Caution: the video has motion, which may affect some people.|Motion Simulation Hazard|



## Examples

```
<meta property="schema:accessibilitySummary">
	The publication contains structural and page navigation. All non-decorative images have alt text or captions, or are described in the surrounding text. The publication meets WCAG 2.0 Level AA.
</meta>
```

```
<meta property="schema:accessibilitySummary">
	This publication is screen reader friendly and is accessible to persons with disabilities. The publication was designed to be as accessible as possible to all persons with disabilities. It is compatible with the wide range of Assistive Technology on the market today. The built in features of most EPUB Reading Applications have accessibility features that may be used, e.g. read aloud is available in many Reading Apps. The publication meets the EPUB Accessibility requirements and it also meets the Web AccessibilityContent Guidelines (WCAG) at the double "AA" level.

	Extensive navigation is provided to make it easy to use. The logos provided have alt text to identify what the logo represents. there are no other images. There are no accessibility hazards.

	There are no video or audio recordings.
</meta>
```

`accessibilityFeatures` we think we want to add reference to in the
summary.

-   alternativeText
-   audioDescription
-   captions
-   describedMath
-   longDescription
-   MathML
-   printPageNumbers
-   readingOrder
-   rubyAnnotations - Foreign Languages / Language Transitions
-   structuralNavigation - (TOC)
-   synchronizedAudioText - (Audio Book)
-   tableOfContents
-   tactileGraphic - (Sue-Ann how to reference in Ed Materials)
-   tactileObject Same - DIAGRAM Meeting question.
-   transcript

---
## Acknowledgements

### Editors
* George Kerscher
* Charles LaPierre
* Gregorio Pellegrino

### Contributors
* Avneesh Singh
* Jason White
* Madeleine Rothberg
* Sarah Runcie


