Bubble Graph Ontology (BGO)
==========================

The Bubble Graph Ontology is a Semantic web application for quantitative data exploration.

The namespace for BGO is *http://linkeddata.center/lodmap-bgo/v1#*

The suggested prefix for the BGO namespace is **bgo** .

BGO contains two core classes:

- **Account** an a-dimensional quantity (amount) with an optional reference value. 
- **Domain** the set of all known Accounts.

BGO goal is to propose the data model for data exploration and visualization; it is NOT related to the meaning of the represented data.
An *account* can be used to describe a Financial Report fact, a politician speaking time on TV or any other versionable quantitative value. 

All accounts in a *Domain* can be presented as a paged list (**TableView**) or as a whole in a big picture (**Overview**).

The overview admits a list of **Partitions** . A Partition is a collection of disjoined **account subset** organized by some *algorithms*. A partition always contains (implicitly or explicitly) a **default account subset** that identifies all accounts in the domain that not explicitly defined in the same partition. 

Besides these,  BGO defines some other concepts to describe user interaction features in a data exploration application. For example, an account admits some *Perspectives* to highlight specific aspects like metadata view, historical trends, breakdowns, and social impacts. Other.

Semantic relationships are crucial to the definition of concepts. However, next to these structured characterizations, concepts have to be further defined using human-readable ("informal") documentation. Any BGO concept (**Things**) can be annotated using a set of properties derived from well-known vocabularies like Dublin Core, Foaf and RDFS:

- **icon**:  a sub-property of foaf:thumbnail
- **depiction** : a sub-property of foaf:depiction;
- **label**: a sub-property of rdfs:label;
- **title**, **description**, **abstract** : as sub-properties of homonymous Dublin Core properties;
 

![UML diagram](doc/uml-diagram.png)

The green boxes represent the concepts that should be the [foaf:primaryTopic](http://xmlns.com/foaf/spec/#term_primaryTopic) object in a data-driven document.


Besides classes and properties, BGO defines the some extensions to the default xsd:String datatype:
 
- **MDString** a strings that should be displayed according [Markdown](https://commonmark.org/) rendering specifications.
- **RGB** a strings that represents a RGB color in the form of "#rrggbb" wer rr g a and b  are exadecimal numbers [0-9a-f
- **Route** a strings that represents an internal routing (application dependent)

BGO is expressed in a [owl file](bgo.rdf) serialized as RDF xml. You can edit the file by hand or using [Protégé](https://protege.stanford.edu/)

For some examples of BGO ontologies, have a look at the example directory.

BGO ontology is used by [LODMAP2D application](https://github.com/linkeddatacenter/LODMAP2D) and by some public and private projects. 

## License

The BGO ontology is available under the Creative Commons Attribution 4.0 Unported license; see http://creativecommons.org/licenses/by/4.0/. 
In a nutshell, you are free to copy, distribute and transmit the work; to remix/adapt the work (e.g. to import the ontology and create specializations of its elements),
as long as you attribute the work in the manner specified by the author or licensor 
(but not in any way that suggests that they endorse you or your use of the work).

Proper Attribution: include the statement "This work is based on the Bubble Graph Ontology (BGO), developed by Enrico Fagnoni for LinkedData.Center" and add a link to http://linkeddata.center/
