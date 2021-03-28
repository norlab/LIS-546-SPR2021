---
layout: default
---
# Emerging Topics

## Data Curation Future Directions
This final module discusses the future in data curation. Data curation is a fast moving field that responds to emerging needs of data producers, consumers, and users. Many emerging topics in data curation are beyond the scope of a 10 week quarter, but are worthy of our time and attention. Below, I cover some interesting topics and provide resources that you can use for future reference.

These are also not just my thoughts - [I asked friends and collaborators to tell me what emergent topics they thought were most important for the future of data curation](https://twitter.com/nniiicc/status/1266069650359500800?s=20). Below are their responses (and my own thoughts).

## Ontologies for Linked Data
In our previous chapter on linked data I described a rapidly evolving "cloud" or graph of linked data published to the web. Linked data are often governed by formal ontologies or vocabularies that include class, sub-class, properties and instances of data. These formalisms allow for data to follow a common markup (a standard), and these standards in turn enable relationships between data to be formally expressed and acted upon by machines.

The difference between a "vocabulary" and an "ontology" is often, ironically, semantic - ontologies are really just formal vocabularies that give linked data practitioners standard terms to define subjects, objects, and predicates for markup of data. As the [W3C notes](https://www.w3.org/standards/semanticweb/ontology):

>There is no clear division between what is referred to as “vocabularies” and “ontologies”. The trend is to use the word “ontology” for more complex, and possibly quite formal collection of terms, whereas “vocabulary” is used when such strict formalism is not necessarily used or only in a very loose sense. Vocabularies are the basic building blocks for inference techniques on the Semantic Web.

Even though I argued in our previous module that the semantic web has failed in many respects - where this field has succeeded is in providing useful ontologies for common data on the web. In the example I used for Austin, TX, the ontology that powered our linked data was `DbPedia`. By providing for standard ways to mark-up the subject, object, and predicates for Austin, TX, we were able to use simple declarations to query DbPedia to find the population of Austin, TX without having to explicitly state this factual information. In practice, this markup looked like the following:

```
<http://dbpedia.org/resource/Austin,_Texas>
<http://xmlns.com/foaf/0.1/based_near>
<http://sws.geonames.org/4671654/austin.html>
```

In terms of linked data - what we used were namespaces from the ontology that were defined on the web. If you click on the first namespace - you see all of what DbPedia knows about Austin, TX.

This allows for a plain language statement like "Austin has a population of 964,254" to take on a machine-readable statement like the following:

- Subject <http://dbpedia.org/resource/Austin,_Texas> 
- Predicate: dbo:PopulatedPlace/populationDensity 
- Object: 964,254

The key here is that DbPedia provided the subject and predicate statements - that is we used a `resource` in DbPedia to describe a particular place (Austin, TX) and we used a predicate from the ontology `dbo:PopulatedPlace/populationDensity` to connect the Subject to an Object (the actual population of Austin, TX). Our machines can interpret and know this semantic information simply through syntax. The ontology does all of the work in defining what a resource is, what a predicate means, and what the resulting object value is. 

Ontologies are rigid in that they require very specific syntax, but they are also incredibly powerful in that they provide for so much of the standardized factual information we expect (and know) to already exist on the web. DbPedia is just one node in the emerging linked data graph. By understanding and using ontologies of linked data, as we discussed last week, we can connect our data (however locally specific it may be) to this web of information. The key to really understanding and using ontologies effectively is to know which ones exist, and to master their syntax. 

Here are some resources to continue exploring linked data and ontologies: 

- W3C [description of ontologies](https://www.w3.org/standards/semanticweb/ontology)
- Bennett, M., & Baclawski, K. (2017). The role of ontologies in linked data, big data and semantic web applications. Applied Ontology, 12(3-4), 189-194. This provides a critical but helpful overview of the role of ontologies in linked data. [PDF](https://content.iospress.com/download/applied-ontology/ao185?id=applied-ontology%2Fao185)
- Munir, K., & Anjum, M. S. (2018). The use of ontologies for effective knowledge modelling and information retrieval. Applied Computing and Informatics, 14(2), 116-126. [PDF](https://www.sciencedirect.com/science/article/pii/S2210832717300649)
- A handy [Linked Data Glossary](https://www.w3.org/TR/ld-glossary/)
- A very accessible and searchable list of [Linked Data Ontologies](https://lov.linkeddata.es/dataset/lov/vocabs)

## Sensitive Data & Privacy

Coming soon!  


## Emulation
Throughout the quarter we have discussed the transformation of data from closed or proprietary formats to open formats (or plain text encodings) which enable data to be reliably reused across different computing environments. There are typically two ways to achieve these transformations: Migration and Emulation. 

Migration is, quite simply, the reformatting of data - which depends upon moving content encoded in one standard to another (e.g. Excel to CSV).

In digital preservation an alternative approach to format migration is the practice of emulation. Emulation is, broadly, the reproduction of a computing environment in which a data format is rendered. This allows software or a program to be used in any hardware or computing environment.

Most of us have experienced emulation in the context of legacy video games. For example, when we play a version of ["Super Mario Bros" in a browser](https://supermarioemulator.com/mario.php) this is the emulation of the original Nintendo console. This allows us to port the functions of Nintendo to our contemporary computing hardware. We no longer need an actual Nintendo console to play the games that were originally developed for that hardware.

Similarly, emulation is being developed for interacting with and using software that is necessary for reproducing analyses, interacting with research artifacts (e.g. simulations or dynamic graphs), and rendering data. Emulation was once exceptionally difficult and prohibitively expensive to develop, but is being made easier by what are called "containers" or "virtual machines" that allow for anyone to reproduce a computing environment in which data were analyzed and used.

Examples and further reading on Emulation:

- Yale's Emulation as a Service https://web.library.yale.edu/emulation
- Code Ocean and the ability to "push a button" and rerun someone's analysis is a good example of emulation as a service for research data. This is a good [webinar video](https://codeocean.com/webinar/editor) on the topic.
- Adam McMaster has a nice [general blog post on using containers for research](Why you should use Docker in your research).

## Advocacy and Solidarity Through Data Curation

Coming soon!

### Data Feminism & Activism

Coming soon!

### Data For Black Lives

Coming soon!
