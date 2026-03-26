---
title: Data Provenance
layout: documentation
permalink: /docs/data-provenance
exclude: true
---

The process through which the Attic Oratory Database was created can be presented in the following steps:

### 1. Annotation Transfer
The first step in data generation uses the Annotation Transfer Pipeline developed by [Laura Soffiantini (2024)](https://sites.google.com/view/pythonforclassicists/home?authuser=1). This pipeline inputs the English translations of texts provided on [ToposText](topostext.org) and the corresponding ancient Greek texts on [Perseus](perseus.tufts.edu) (accessed via the [Perseus Github](https://github.com/PerseusDL/canonical-greekLit/tree/master/data)). 

This pipeline uses the [FlairNER](https://huggingface.co/flair/ner-english) model to annotate the English translations from ToposText, the [LaBSE Sentence Transformers model](https://huggingface.co/sentence-transformers/LaBSE) and [Vecalign](https://github.com/thompsonb/vecalign) to align English and Greek sentences, and [UGARIT Translation Alignment](https://huggingface.co/UGARIT/grc-alignment) to align tokens. 

The output of this pipeline are tabular CSV files with the text tokens and annotations in the BIO format.

![Annotation Transfer Visualization](/images/annotation_transfer_pipeline.jpg "Annotation Transfer Visualization") *Visualization of Annotation Transfer Pipeline*

### 2. NER to XML
The second step of the process is to convert the NER annotations stored in CSV files to TEI-XML files. This is accomplished through a Python script (available on the project Github) which projects the CSV annotations onto the Perseus TEI-XML files in the form of TEI tags (i.e. `<persName>`).

![NER to XML Visualization](/images/ner-to-xml.jpg "NER to XML visualization")
*Visualization of NER to XML Script*

### 3. Semi-Automatic Semantic Annotation
The third step is a Python script (available on the project Github) which guides a user through the semi-automatic semantic annotation and disambiguation of the tagged people in the corpus. For each text, the script iterates through each `<persName>` tag in the annotated TEI-XML files and prompts the user to confirm whether or not it refers to a person, then enter an identifier from the [Persons of Ancient Athens prosopography](https://attica.artsci.utoronto.ca/paa-search.php)(PAA).  If the person is not in the PAA, the person can enter either a [Wikidata](https://www.wikidata.org/) identifier (for more well-known historical/mythological figures), or mint a new identifier. 

If the person identifier is not already in the Attic Law ontology, a new person entity is added to the ontology. The user is then prompted to enter the English and ancient Greek name of that person to be entered as labels. 

For each TEI-XML file processed, a file of standoff annotations in the form of [W3C Web Annotations](https://www.w3.org/TR/annotation-model/) is generated. These annotations point to the person entity in the ontology, and use XPath Selectors to point to the location of the person reference within the texts. 

![Annotation Decision Tree](/images/annotation-decision-tree.png "Annotation Decision Tree")
*Decision Tree for Semi-automatic Annotations*

![Prosopography Builder](/images/prosopography_builder.jpg "Prosopography Builder")
*Visualization of Prosopography Builder*

```
atticlaw:anno_Dem_59_1 a oa:Annotation ;
    dcterms:created "2025-10-18"^^xsd:date ;
    dcterms:creator <https://orcid.org/0009-0000-0420-4711> ;
    oa:hasBody atticlaw:702905 ;
    oa:hasTarget [ a oa:SpecificResource ;
            oa:hasSelector [ a oa:XPathSelector ;
                    oa:value "/TEI/text/body/div/div[@n='1']/p/persName[1]" ] ;
            oa:hasSource <http://www.ontologia.fr/OTB/classical_orators#Dem_59> ] .
```
*Sample Web Annotation*

### 3b. Semantic Annotation of Unnamed Women
A substep of Step 3 is to semi-automatically generate Web Annotations of the unnamed women in the corpus. This is accomplished alongside the previous steps: a list of ancient Greek terms for women (such as mother, daughter, sister etc.) is processed alongside Step 1, adding a column to the resulting CSV file noting the presence of words referring to women. In Step 2, these tokens identified as references to women are given TEI-XML tags `<persName type='woman'>`. 

In Step 3b, an altered version of the Python script in Step 3 generates annotations of unnamed women. This creates 'Woman' entities in the ontology, which mostly have newly minted identifiers unique to the ontology (following the structure of "unw1").

### 4. Webpage Processing
The final step of the data generation process to create the Attic Oratory Database is to convert all of the data stored as TEI-XML and RDF into Endings-compliant web presentation formats (i.e. HTML with CSS and JavaScript).

The TEI-XML text files are converted into HTML via a custom XSLT (found in the Github).

Through SPARQL queries, information is extracted from the Attic Law Ontology to create the indices and entity pages. This extracted information is then converted into HTML pages. The queries and Python code used to create these pages are also available on the Github.

Lastly, a Python script is used to extract reference snippets, the text surrounding each person mention in the annotations, for presentation on each person entity page.

Through these Python scripts, the website can be entirely rebuilt from the datasets.




