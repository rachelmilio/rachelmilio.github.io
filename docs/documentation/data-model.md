---
title: Data Model
layout: documentation
permalink: /docs/data-model
exclude: true
---
The Attic Law Database draws from five ontologies: the Legal Processes ontoterminology, the Legal Bodies ontoterminology, the Legal Participants ontoterminology, the Oratory Corpus ontoterminology, and the Attic Law Ontology. 

![Data Model Visualization](/images/ontology_data_model.jpg "Data Model Visualization")

The Attic Law Ontology was built in [Protégé](https://protege.stanford.edu/) as a standard OWL ontology, while the four ontoterminologies are built in [TEDI](https://ontoterminology.com/tedi), the Ontoterminology Editor, and therefore use the OTV vocabulary.

An ontoterminology is a terminology whose conceptual system is a formal ontology [(Roche, 2012)](http://ontologia.fr/Bibliographie/567_Paper_Header.pdf). In an ontoterminology, the conceptual dimension (concepts, objects) and the linguistic dimension (terms, proper names) are linked. 

In addition to the five ontologies, the Attic Oratory Database uses web standards such as the [Web Annotation Data Model](https://www.w3.org/TR/annotation-model/) and [TEI-XML](https://tei-c.org/) to store standoff annotations. Annotations of person references are stored as Web Annotations, linked back to the texts stored in TEI-XML through XPath selectors.

To learn more about each data model, navigate to their unique pages:

### [Legal Processes Ontoterminology](/docs/data-model/legal-processes)

### [Legal Bodies Ontoterminology](/docs/data-model/legal-bodies)

### [Legal Participants Ontoterminology](/docs/data-model/legal-participants)

### [Oratory Corpus Ontoterminology](/docs/data-model/oratory-corpus)

### [Attic Law Ontology](/docs/data-model/attic-law)