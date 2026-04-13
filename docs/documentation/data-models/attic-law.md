---
title: Attic Law Ontology
layout: documentation
permalink: /docs/data-model/attic-law
exclude: true
---
<html>
    <head>
        <style>
           body { font-family: "New Athena Unicode", "Cardo", "Palatino Linotype", serif; } 
           .header { font-size: 1.8em; text-align: center; padding-bottom: .7em;}
           .block-meta { 
                color: #131313; 
                margin: 0.5rem 0;
                font-size: 1.3em;
                border-bottom: 2px solid #34495e;
                padding-bottom: 1rem;
            }
            * {box-sizing: border-box;}
            .img-container {
                display: flex;
                justify-content: center;
                align-items: center;
                height: auto;
            }
            .image-container img:hover {
                cursor: zoom-in;
            }
            .img {
                max-width: 100%;
            }
            .caption {
                text-align: left;
                padding-bottom: 2rem;
            }
        </style>
    </head>
    <body>
    <div><p>The Attic Law ontology synthesizes the project ontoterminologies in order to describe and define the relations between legal events, speeches, and people within the corpus of Attic Oratory.</p>
    <p>The central class of <b>Legal_Event</b> is a superclass of the Legal Processes defined in the Processes ontoterminology. A <b>Legal_Event</b> has the properties <i>hasParticipant</i>, to connect to people who hold roles defined in the Participants ontoterminology, and <i>arguedIn</i>, to connect to the speech (or speeches) in which the case is argued, as defined in the Oratory Types ontoterminology.</p>
    <p>To increase interoperability, the Attic Law ontology connects to other standard ontologies such as <a href="https://cidoc-crm.org/">CIDOC-CRM</a> and <a href="https://xmlns.com/foaf/spec/">FOAF</a>.</p>
    <p>The Attic Law ontology was created in the standard ontology editor <a href="https://protege.stanford.edu/">Protégé</a>.</p>
    <div class="img-container" id="image-container">
            <img class="img" id="event" src="/images/event_model.png" alt="Visualization of Event Model">
        </div>