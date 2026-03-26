---
title: Site Functionality
layout: documentation
permalink: /docs/functionality
exclude: true
---
When first entering the Attic Oratory Database, the landing page is the homepage. The homepage gives some introductory information for the project, some featured pages, and allows for further navigation into the features of the site. 

The Attic Oratory Database has four primary sections, accessed through the navigation bar in the header from any page:
### 1. [Case Studies](/case-studies-page)
The Case Studies page is an index of the project case studies, examples which use unique Semantic technologies to present aspects of texts in the corpus. These include a Family Tree visualization of the families in Isaeus 11 and Demosthenes 43, using a [Family Chart visualization](https://github.com/donatso/family-chart) based in D3.js; a mapping interface containing the locations frequented by Neaira in Demosthenes 59 created with the open-source browser-based mapping tool [Peripleo](https://github.com/britishlibrary/peripleo/tree/main); and a visualization of the use of 
[Factoid Prosopography](https://www.kcl.ac.uk/factoid-prosopography) to model the individual Phano (also from Demosthenes 59). 

The Case Studies do not represent the main functionality of the site, but rather examples of potential future directions to enrich the content of the Database. 

### 2. [Dictionaries](/dictionaries-page)
The Dictionaries page is a landing page in order to access the four dictionaries which describe key terms within the domain of Attic Law. These dictionaries are created via the [TEDI HTMl dictionary export](https://ontoterminology.com/export) feature. Each dictionary presents the English terms, aligned with their concept, equivalent terms in English and ancient Greek, hypernyms and hyponyms. Additionally, each dictionary entry links to an individual entry page which can be linked to elsewhere in the site. 

The four dictionaries are:
1. [Legal Processes Dictionary](/processes-dictionary): a dictionary describing the legal processes (i.e. types of lawsuits) in Classical Athens.
2. [Legal Bodies Dictionary](/bodies-dictionary): a dictionary describing legal bodies (i.e. institutions in the government involved in legal processes) in Classical Athens. 
3. [Legal Participants Dictionary](/participant-dictionary): a dictionary describing the roles held by participants (not legal bodies) in the Athenian legal system.
4. [Oratory Corpus Dictionary](/oratory-dictionary): a dictionary describing the types of speeches within the oratory corpus.

For more on the ontoterminologies behind these dictionaries, navigate to the [Data Model](/docs/data-model) section of the documentation.

### 3. [Indices](/index-page)
The Indices page is a landing page to access the indices which present the majority of the data on the Attic Oratory Database. Each index is a list of relevant entities, with some search and filtering functionality to streamline access to the desired entity pages.

The four indices are:
1. [Author Index](/author-index)

    The Author Index page lists the canonical authors of the Oratory Corpus (plus Apollodorus, who is considered with a high degree of certainty to be the author of some Demosthenic texts). This page allows for name-based searching in English and ancient Greek. 

    Each card in the Author Index links to an author page, also accessible via the Person Index. These pages contain biographical information, such as birth and death year, links to external identifiers, and familial relations when known. Additionally, author pages have relevant information such as the legal roles, speaking roles, and authorship roles of each author, as well as a compilation of in-text references to the author within the corpus. 

2. [Corpus Index](/corpus-index)

    The Corpus Index page lists the texts from the Attic Oratory corpus available on the Attic Oratory Database. This index page allows for search and filtering: search based on English or Greek text titles; and filtering based on speech types (as defined in the [Oratory Corpus Dictionary](/oratory-dictionary)) and authorship. For the speech type checkboxes, a checked box will alter the shown speeches to only show speeches that fit in that category. Checking multiple boxes functions  like an "OR" operator, showing all texts that fit at least one of the checked categories. The author attributes filters work with an "AND" operator, meaning a user can search for a text with the canon author Demosthenes and the probable author Apollodorus. The speech type filters work simultaneously with the author attribute filters as an "AND" operator To clear author attribute filters, use the "Clear" button. 

    Each card in the Corpus Index links to a text page. These pages provide information on the text, such as its potential authorship attribution, its speech type, its speaker, and the legal event for which it was written. Additionally, these pages have an embedded version of the speech in ancient Greek, derived from Perseus and presented in an HTML format (to learn more about data generation, view the [Data Provenance](/docs/data-provenance) documentation). Alongside the text is a list of the people mentioned in these texts. 

3. [Event Index](/event-index)

    The Event Index page lists the legal events substantiated by the texts in the corpus. Events can be searched for based on their English titles. 

    Each card in the Event Index links to an event page. An event page contains information on the legal event type, linking to the Legal Processes dictionary entry. Additional information on the speech (or speeches) which were written for this legal event and the participants and their roles is also presented.

4. [Person Index](/person-index)

    The Person Index page lists all of the people in the Prosopography of Attic Oratory (i.e. the named and unnamed people mentioned within these texts, extracted via the semi-automatic semantic annotation process described in the [Data Provenance](/docs/data-provenance) documentation). This index page allows for search and filtering: search based on English and ancient Greek names, and filtering based on gender and legal roles. In this way, a user could filter for all women who are also defendants or all people who are both witnesses and plaintiffs. 

    Each card in the Person Index links to a person page. This page contains information such as the gender of the person, their identifiers (from PAA if available, otherwise through Wikidata), their legal roles, their familial relations, and in-text references to the person corresponding to the semi-automatic semantic annotations.

### 4. [Documentation](/docs)
The Documentation page is a landing page for documentation and information on the site.

Additionally, from the header, the title text "Attic Oratory Database" can return a user to the homepage at any point.

The footer, present on every page within the site, also contains essential information for site use: contact information for the creator through an email and Github link, the version number and latest update date, and the project licensing (Creative Commons BY-SA 4.0).