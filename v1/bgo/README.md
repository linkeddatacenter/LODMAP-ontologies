Bubble Graph Ontology (BGO)
==========================

The Bubble Graph Ontology is a Semantic web application suitable to describe any quantitative data as blobs of colorful shapes. 
A shape is called **Account**, and its area should be, more or less, proportional to its quantitative value. The color of the shape depends on its properties, for instance, the change rate against a reference value.

The namespace for BGO is *http://linkeddata.center/lodmap-bgo/v1#*

The suggested prefix for the BGO namespace is *bgo*

BGO is modeled around the following classes:
- **Account**  a versionable quantity representable with a shape (e.g., a bubble) 
- **Domain** the set of all Accounts that share the same meaning, for instance, all the facts defined in the financial reports of a company.
- **Partition** a collection of disjoined Account set related through the use of some **Algorithms**

An account admits some **Perspectives** that highlight specific aspects (e.g., historical, decomposition, social)

Beside this, bgo defines some standard views to display accounts:

- the **Overview** that displaies all Accounts in a domain big picture 
- the **Table view** that is just a paged view of the Overview.

Many attributes in BGO are sub-properties of homonymous properties defined in well-known vocabularies like Dublin Core Terms, W3C Cube vocabulary, and SKOS.

Semantic relationships are crucial to the definition of concepts. However, next to these structured characterizations, 
Concepts sometimes have to be further defined using human-readable ("informal") documentation. All concepts in bgo can be annotated with:

- **icon** : a sub-property of foaf:thumbnail;
- **depiction** : a sub-property of foaf:depiction;
- **label**: a sub-property of skos:prefLabel;
- **title**, **description**, **abstract* : as sub-properties of homonymous Dublin Core properties;
- **link* : as sub-properties of rdfs:seeAlso

The following picture shows the main concepts and attribute relations defined by bgo:

![UML diagram](doc/uml-diagram.png)


BGO is expressed in a [owl file](bgo.rdf) serialized as RDF xml. You can edit the file by hand or using [Protégé](httpsbgo://protege.stanford.edu/)

Note that BGO objective is to define the data model for data exploration and visualization; it is NOT related the meaning of the represented data.
An *account* can be used to describe a Financial Report fact, a politician speaking time on TV or any other versionable quantitative value. The data semantic should be linked using *dct:source propery*.

For some examples of bgo ontologies, have a look at the example directory.

BGO ontology is used by [LODMAP2D application](https://github.com/linkeddatacenter/LODMAP2D) and by some public and private projects. 

## License

The BGO ontology is available under the Creative Commons Attribution 4.0 Unported license; see http://creativecommons.org/licenses/by/4.0/. 
In a nutshell, you are free to copy, distribute and transmit the work; to remix/adapt the work (e.g. to import the ontology and create specializations of its elements),
as long as you attribute the work in the manner specified by the author or licensor 
(but not in any way that suggests that they endorse you or your use of the work).

Proper Attribution: include the statement "This work is based on the Bubble Graph Ontology (BGO), developed by Enrico Fagnoni for LinkedData.Center" and add a link to http://linkeddata.center/
