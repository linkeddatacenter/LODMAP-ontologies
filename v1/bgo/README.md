Bubble Graph Ontology (BGO)
==========================

The Bubble Graph Ontology is a Semantic web application suitable describe any quantitative data as blobs of colorful shapes. 
A shape is called **Account** and its area should be, more or less, proportional to its quantitative value. The color of the shape depends from its properties, for instance the change rate 
against a reference value.

The namespace for BGO is *http://linkeddata.center/lodmap-bgo/v1#*

The suggested prefix for the BGO namespace is *bgo*

BGO is modelled around following classes:
- **Account**  a versionable quantity that can be represented with a shape (e.g. a bubble) 
- **Domain** the set of all Accounts that share the same meaning, for instance aall the facts defined in the financtial reports of a company.
- **Partition** a collection of disjoined Account set relathed through the use of some **Algoritms**

An account admits some **Perspectives** that highlight specific aspects (historical, decomposition, social, etc.)

Beside this bgo define some standard views useful do display accounst:

- the **Overview** that display all Accounts in a domain big picture 
- the **Table view** thats is just a tabular view of the Overview, divided in pages.

Many attributes in BGO are modeled as sub-properties of homonymous properties defined in well known vocabularies like Dublin Core Terms, W3C Cube vocabulary and SKOS.

Semantic relationships are crucial to the definition of concepts. However, next to these structured characterizations, 
concepts sometimes have to be further defined using human-readable ("informal") documentation. All concepts in bgo can be annotated with:

- a title 
- a short description
- an abstract
- some links to information provenance Uri using the dct:source

The following picture shows main concepts and attribute relations defined by bgo:

![UML diagram](doc/uml-diagram.png)


BGO is expressed in a [owl file](bgo.rdf) serialized as RDF xml. You can edit the file by hand or using [Protégé](httpsbgo://protege.stanford.edu/)

Note that BGO objective is to define the data model for a data exploration and  visualization; it is NOT retated the meaning of the represented data.
An a Account can be used to describe a Financial Report fact, a politician speaking time on TV or any other versionable quantitative value. The data semantic should be linked using *dct:source propery*.

For some example of bgo ontology, have a look to the example directory.

BGO ontology is used by [LODMAP2D application](https://github.com/linkeddatacenter/LODMAP2D) and by a number of public and private projects. 

## License

The BGO ontology is available under the Creative Commons Attribution 4.0 Unported license; see http://creativecommons.org/licenses/by/4.0/. 
In a nutshell, you are free to copy, distribute and transmit the work; to remix/adapt the work (e.g. to import the ontology and create specializations of its elements),
as long as you attribute the work in the manner specified by the author or licensor 
(but not in any way that suggests that they endorse you or your use of the work).

Proper Attribution: simply include the statement "This work is based on the Bubble Graph Ontology (BGO), developed by Enrico Fagnoni for LinkedData.Center" and add a link to http://linkeddata.center/
