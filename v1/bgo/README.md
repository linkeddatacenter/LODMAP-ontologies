Bubble Graph Ontology (BGO)
==========================

The Bubble Graph Ontology (BGO) is a Semantic Web Application for quantitative data exploration in a data-driven document.

The namespace for BGO is *http://linkeddata.center/lodmap-bgo/v1#*

The suggested prefix for the BGO namespace is **bgo** .

BGO contains two core classes:

- **Account** an a-dimensional quantity (amount) with an optional reference value. 
- **Domain** the whole set of all accounts in the document.

BGO proposes a data model for data exploration and visualization; it is NOT related to the meaning of the represented data.
An *account* can be used to describe a Financial Report fact, a politician speaking time on TV or any other versionable quantitative value. 

All accounts in a *Domain* can be presented in a paged document (**TableView**) or as a whole in a big picture (**Overview**).

The overview admits a list of **partitions** . A Partition is a collection of disjoined **account sub subset** organized by some *algorithms*. A partition always contains (implicitly or explicitly) a **default account subset** that identifies all accounts in the domain that not explicitly defined in the  partition. 

Besides these,  BGO defines some other concepts to suggest user interaction features. For example, an account admits some **perspectives** to highlight specific aspects like metadata, historical trends, breakdowns, and social impacts.

Semantic relationships are crucial to the definition of concepts. However, next to these structured characterizations, concepts have to be further defined using human-readable ("informal") documentation. Any BGO concept (**Things**) can be annotated using a set of properties derived from well-known vocabularies like Dublin Core, Foaf and RDFS:

- **icon**:  a sub-property of foaf:thumbnail.
- **depiction** : a sub-property of foaf:depiction;
- **label**: a sub-property of rdfs:label;
- **title**, **description**, **abstract** : as sub-properties of homonymous Dublin Core properties;

A BGO renderer can use these properties to build user interface components, providing defaults if needed and taking into account the following notes:

- *icon* is a symbol for a *label*, that in turn is an abbreviation of the *title*;
- the **depiction* is an image for *description*, that is expanded in the *abstract*; the abstract can contain links and references to other documents.

![UML diagram](doc/uml-diagram.png)

The green boxes represent the concepts that should be the [foaf:primaryTopic](http://xmlns.com/foaf/spec/#term_primaryTopic) object in a data-driven document.
The relations in bolds have cardinality "exactly 1". If no value provided an BOG  reasoner is supposed to provide a default.

Besides classes and properties, BGO defines the some extensions to the default xsd:String datatype:
 
- **MDString** a strings that should be displayed according [Markdown](https://commonmark.org/) rendering specifications.
- **RGB** a strings that represents a RGB color matching the following regexp: *^#[0-9a-f]{6}$* (e.g. `#b2182b`)
- **Route** a strings that represents an internal routing. The expected behavior is application dependent.

It also defines some individuals for algorithms.


BGO is expressed in a [owl file](bgo.rdf) serialized as RDF xml. You can edit the file by hand or using [Protégé](https://protege.stanford.edu/)

For some examples of BGO ontologies, have a look at the example directory.

BGO ontology is used by [LODMAP2D application](https://github.com/linkeddatacenter/LODMAP2D) and by some public and private projects. 

## License

The BGO ontology is available under the Creative Commons Attribution 4.0 Unported license; see http://creativecommons.org/licenses/by/4.0/. 
In a nutshell, you are free to copy, distribute and transmit the work; to remix/adapt the work (e.g. to import the ontology and create specializations of its elements),
as long as you attribute the work in the manner specified by the author or licensor 
(but not in any way that suggests that they endorse you or your use of the work).

Proper Attribution: include the statement "This work is based on the Bubble Graph Ontology (BGO), developed by Enrico Fagnoni for LinkedData.Center" and add a link to http://linkeddata.center/
