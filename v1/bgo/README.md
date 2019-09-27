Bubble Graph Ontology (BGO)
==========================

The Bubble Graph Ontology is a Semantic web application suitable to describe any quantitative data as blobs of colorful shapes. 
A shape is called **Account**, and its area should be, more or less, proportional to its quantitative value. The color of the shape depends on its properties, for instance, the change rate against a reference value.

The namespace for BGO is *http://linkeddata.center/lodmap-bgo/v1#*

The suggested prefix for the BGO namespace is *bgo*

BGO is modeled around the following core classes:

- **Account** an a-dimensional amount with an oprional reference value; normally representable with a shape (e.g., a bubble) 
- **Domain** the set of known Accounts; for instance, all the facts defined in the financial reports of a company.

All accounts in a *Domain* can be rapresented as a paged list of accounts (**TableView**) or as whole in a big picture (**Overview**).

The overview allow to select one **Partition** from a list. A Partition is collection of disjoined **account sub set** in a domain organized through some *Algorithms*. A partition alwais contains (implicitelly or explicitelly) a **Default Account sub Set** that collects all account in the domain that are not explicitelly defined in an account subset of the partition. 

Beside these, bgo defines some concepts to describe how to present/visualize/navigate specific
aspects of an Account or a o a domain. For instance, an account admits some *Perspectives* that highlight specific aspects like metadata view (mandatory), historical evolution, breackdown, decomposition, social impacts.


Semantic relationships are crucial to the definition of concepts. However, next to these structured characterizations, concepts have to be further defined using human-readable ("informal") documentation. A bgo (**Things**) can be annotated a set of properties derived from well-known vocabularies like Dublin Core Terms, Foaf, and SKOS.:

- **icon** : a sub-property of foaf:thumbnail;
- **depiction** : a sub-property of foaf:depiction;
- **label**: a sub-property of skos:prefLabel;
- **title**, **description**, **abstract** : as sub-properties of homonymous Dublin Core properties;

Icons and depiction expect a URL image as a range, all other properties should be RDF string litterals or
 bgo:MDString that is a custom data type to define a string that should be diplayed according
 [Markdown](https://commonmark.org/) rendering specifications.

The following picture shows the main concepts and attribute relations defined by bgo:

![UML diagram](doc/uml-diagram.png)

The green boxes represent the concepts that should be the [foaf:primaryTopic](http://xmlns.com/foaf/spec/#term_primaryTopic) of a data driven document.

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
