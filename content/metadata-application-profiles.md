---
layout: default
---
# Metadata Application Profiles
**Original Author: Nic Weber**  
**Editing & Updates: Bree Norlander**  

There are an abundance of explanations and tutorials for how metadata should be created under domain specific constraints, but there is surprisingly little attention paid to principles that underlie all knowledge organization and representation activities that are required to create valid metadata. Drawing inspiration from the data science concept of "Tidy Data" this chapter introduces a set of principles for creating Tidy Metadata. These principles are domain-agnostic - they can and should be applied to any setting in which accurate description, retrieval, and discovery are necessary.

## Introduction
The underlying principles of creating metadata come from fields such as knowledge organization and representation, and are applied practically to domain specific data. [Ecology data](https://eml.ecoinformatics.org/) have different needs than do, for example, [cultural heritage](https://www.dublincore.org/about/) materials. As a result, many discipline or domain specific metadata standards have been developed to accommodate these different resources.

At a broad level of abstraction, metadata provides for both human and machine-interpretable information necessary for accurate retrieval, discovery, and use of digital objects. But, often metadata creators are not formally trained in either knowledge organization or knowledge representation. For data curators, this poses a number of challenges:

- In upstream curation, curators often need to identify, select, and create a standard for data creators (or collectors) to follow.
- In downstream curation, curators often need to **refactor** metadata, either to make the metadata comply with an existing standard, or to structure the metadata so that it applies to one and only one conceptual entity.

In the [Introduction module](https://norlab.github.io/LIS-546-SPR2021/content/overview_and_intro.html#Introduction) there are simple [definitions](https://norlab.github.io/LIS-546-SPR2021/content/overview_and_intro.html#Definitions) of core concepts related to metadata that will be helpful to review before reading the rest of this module.

## Semantics and Syntax of Metadata
In the most simple form, metadata consists of 'attribute - value' pairs that describe some property of data, or a set of data. Recall that in the introduction, we established that attributes are "the defining features of a class or sub-class, and refer to instances. An instance is a member of a class if it has **all** of the attributes of that class."

Attributes and values can be expressed, semantically, as descriptive, administrative, or technical information about data.

- Descriptive information includes attributes like the title, creator, date of creation, etc.
- Administrative information includes what institution produced the data, who curated the data, what licenses apply to the data, etc.
- Technical information includes how the data were collected, processed, or analyzed. Provenance metadata is often treated as a technical or administrative attribute of a dataset.

Syntactically, we can express or encode attributes using a number of standards. Machine-readable metadata are most often syntactically expressed as JSON or XML. Human-readable metadata can be expressed as a simple table, and its encoding can take a variety of forms - from plain text files to Excel tables.

## Tidy Metadata
Tidy data establishes some general principles that *should* apply to the structure and representation of tables. These principles should be applicable across all kinds of tables that have variables, values, and various kinds of observations. The most simple formulation of tidy data is:

- Each variable is a column
- Each observation is a row
- Each type of observational unit is a table

Metadata should have some similar principles. That is, there should be some general rules that we can follow to describe attributes, values, and their corresponding relationship to instances of a class. Below are the principles I will propose for tidy metadata as it applies to tables of data.

The properties of a dataset are expressed as an attribute-value pair that conforms to a schema:

1. Attributes are declared by a namespace.  
2. Values are, where possible, constrained by a controlled vocabulary (this does **not** apply to free-text fields).
3. Schemas are published to the web.

Let's unpack each of these statements so that it makes sense in the context of data curation.

**"Schemas are published to the web"**: a metadata schema establishes and defines data elements (attributes) and the rules governing the use of data elements to describe a resource (for detailed metadata strategies see: Gourley, D., Zhang, A. (2014). *[Creating Digital Collections: A Practical Guide](https://alliance-primo.hosted.exlibrisgroup.com/permalink/f/lvbsh/TN_cdi_askewsholts_vlebooks_9781780631387)*. United Kingdom: Elsevier Science.). Schemas are, in plain language, the rules of engagement for creating metadata. That is, they govern what are the valid and invalid use of an attribute-value pair to describe a dataset. Schemas then have to be public in order to be validated. Publishing a schema to the web means that the schema must be at a resolvable web address (a url) and should be encoded in a machine-readable language (e.g. XML or JSON). Schemas should, where possible, use definitions of elements (attributes) as a unique namespace.

**"Attributes are declared by a [namespace](https://en.wikipedia.org/wiki/Namespace)"**: In publishing a schema to the web, we should also take care to define the use of an attribute such that each attribute has a unique location where the definition and explanation of its use is publicly accessible and identifiable in a schema. The attribute namespace has a subtle, but important relationship to a schema. A schema can be made up multiple namespaces, each namespace can be a part of a different schema (I'll offer an example below so that this is less abstract).

**"Values are, where possible, constrained by a controlled vocabulary"**: Recall that in the module on Tidy Data, we discussed the appeal to authority control for standard units of measurement. In metadata we want to rely upon this authority control in a similar way - this helps to standardize what types of values an attribute can have, and provide clear guidance for how these values should be constrained.

### Tidy Metadata Examples
A simple way to express metadata describing the painting "Mona Lisa" might look something like this:

<style type="text/css">
.tg  {border-collapse:collapse;border-color:#ccc;border-spacing:0;}
.tg td{background-color:#fff;border-color:#ccc;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#f0f0f0;border-color:#ccc;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.tg .tg-wa1i{font-weight:bold;text-align:center;vertical-align:middle}
@media screen and (max-width: 767px) {.tg {width: auto !important;}.tg col {width: auto !important;}.tg-wrap {overflow-x: auto;-webkit-overflow-scrolling: touch;}}</style>
<div class="tg-wrap"><table class="tg">
<thead>
  <tr>
    <th class="tg-wa1i">Attribute</th>
    <th class="tg-wa1i">Value</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-cly1">Creator</td>
    <td class="tg-cly1">Leonardo da Vinci</td>
  </tr>
  <tr>
    <td class="tg-cly1">Year_Created</td>
    <td class="tg-cly1">c. 1503-1519</td>
  </tr>
  <tr>
    <td class="tg-cly1">Medium</td>
    <td class="tg-cly1">Oil on poplar</td>
  </tr>
  <tr>
    <td class="tg-cly1">Dimmensions</td>
    <td class="tg-cly1">77 x 53</td>
  </tr>
  <tr>
    <td class="tg-cly1">Location</td>
    <td class="tg-cly1">Musée du Lovre, Paris</td>
  </tr>
</tbody>
</table></div>
<br>

The metadata elements in this table are arranged as pairs of attributes and values that generically describe the painting "Mona Lisa".

Putting our tidy metadata principles to work - we could do the following:

**Values constrained by a controlled vocabulary**: Just as with tidy data, we want the values of our table to have an authority control. The value of `Creator` is a good initial candidate. We could express this name in a number of ways, but ultimately we want it adhere to a standard. The [Union List of Artists Names](http://www.getty.edu/research/tools/vocabularies/ulan/about.html) (ULAN) provides an authority file that describes artists, and their attributes (derivative names, nationality, etc.). We should then be able to find a controlled vocabulary in ULAN for [Leonardo da Vinci](http://www.getty.edu/vow/ULANFullDisplay?find=Leonardo+Da+Vinci&role=&nation=&prev_page=1&subjectid=500010879) and be able to control (or constrain) the value in our metadata record based on this definition. We could take the same approach for `Location`, `Medium`, `Dimensions` - each value - in our metadata.

**Attributes declared by a namespace**: The attributes in our metadata table should also have a definition that is available at a namespace. For `Creator` we could appeal to a standard like [Dublin Core](https://www.dublincore.org/) - which is used broadly to create descriptive information about cultural heritage objects. The plain language definition for a creator in Dublin Core is available [here](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#http://purl.org/dc/terms/creator), and the namespace for this attribute is `https://purl.org/dc/terms/creator`. In declaring the namespace for the `Creator` attribute we are saying that this is not our own unique idea of who created a painting, but a specific definition (that of Dublin Core) of what a creator of a work of art means.

**Brief Note on Readability**

In metadata creation, there is often a distinction made between *human-readability* and *machine-readability*. These distinctions are exactly as they appear - human-readable metadata is that which can be easily interpreted by an actual person. The table above is an example of a human readable metadata record. Machine readable metadata means that (similar to our discussions of encoding data in [Tables, Trees, and Triples](https://norlab.github.io/LIS-546-SPR2021/content/tables-trees-triples.html)) a machine can interpret and act upon a metadata record. When we appeal to namespaces, and publish schemas to the web - what we are doing, as data curators, is creating a machine-readable metadata record. These two approaches to creating metadata don't necessarily have to be a tradeoff. Think about how we create independence in data representation (at the logical level) and remember that we can use "data" to feed into "graphic user interfaces". Metadata is no different. We can create machine-readable metadata, and publish this metadata so that it is accessible in a graphic user interface. Privileging the creation of machine-readable metadata, as I do with tidy metadata principles, is simply in service of trying to create sustainable metadata records. We can always translate a machine-readable record into a human-readable record, but the same is not true in reverse. It takes substantially more effort to transform a human-readable record into something a machine can interpret.

**Publish a schema to the web**: In using controlled vocabularies for our values, and namespaces for our attributes, we want a tidy way to reference these in a machine-readable format. This is what we can achieve by making our schema available on the web. For the sake of this example, let's assume that we are only going to use attributes from the Dublin Core standard. If this is the case, then we can depend on the schema for Dublin Core that is already publicly available on the web at [`http://purl.org/dc/elements/1.1/`](http://purl.org/dc/elements/1.1/) - this is a web address with a machine-readable set of definitions for each attribute in our metadata record.

### A Valid Dublin Core Record

Let's continue to work from the assumption that we are creating a metadata record for the Mona Lisa. When we are finished, our tidy metadata record should look something like this, when expressed as XML

```
<?xml version="1.0" encoding="UTF-8"?>

<metadata
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xmlns:dc="http://purl.org/dc/elements/1.1/"
xmlns:dcterms="http://purl.org/dc/terms/">

<dc:title>Portrait of Lisa Gherardini, wife of Francesco del Giocondo, known as the Mona Lisa (the Joconde in French)</dc:title>
<dcterms:alternative>Mona Lisa</dcterms:alternative>
<dc:creator>Leonardo da Vinci</dc:creator>
<dc:description>This portrait was doubtless started in Florence around 1503. It is thought to be of Lisa Gherardini, wife of a Florentine cloth merchant named Francesco del Giocondo - hence the alternative title, La Gioconda. However, Leonardo seems to have taken the completed portrait to France rather than giving it to the person who commissioned it. After his death, the painting entered François I's collection.</dc:description>
<dc:publisher>Musee du Lourve</dc:publisher>
<dc:contributor>Musee du Lourve</dc:contributor>
<dcterms:created xsi:type="dcterms:W3CDTF">1503-01-01</dcterms:created>
<dcterms:created xsi:type="dcterms:W3CDTF">1509-12-31</dcterms:created>
<dc:type xsi:type="dcterms:DCMIType">Image</dc:type>
<dcterms:medium xsi:type="dcterms:IMT">Oil on Poplar</dcterms:medium>
<dc:identifier xsi:type="dcterms:URI">https://www.louvre.fr/en/oeuvre-notices/mona-lisa-portrait-lisa-gherardini-wife-francesco-del-giocondo</dc:identifier>
<dc:source xsi:type="dcterms:URI">https://www.louvre.fr/en/oeuvre-notices/mona-lisa-portrait-lisa-gherardini-wife-francesco-del-giocondo</dc:source>
<dc:language xsi:type="dcterms:ISO639-2">FRA</dc:language>
<dc:language xsi:type="dcterms:ISO639-2">ITA</dc:language>
<dc:language xsi:type="dcterms:ISO639-2">ENG</dc:language>

</metadata>
```

Tidy Metadata:

- In the header of our XML record we provided a machine-readable link to a schema at `http://purl.org/dc/elements/1.1/`
- Each attribute is defined as a set of elements in the Dublin Core schema, and these elements are linked as namespaces in our our Schema.
- Where possible, we have used an authority control on the values of our record. For example, the `Language` attribute is constrained by the controlled vocabulary `ISO639-2` - which provides for country and language codes. In the [standard](https://en.wikipedia.org/wiki/List_of_ISO_639-2_codes) I identified French, Italian, and English.  Notice, the same is true for the date attribute `created`. In this case, we appealed to the [W3C Date Time Format](https://www.w3.org/TR/NOTE-datetime) to control our date(s). This specifies a date should be expressed as `YYYY-MM-DD` - but also note that we took advantage of the date range in our metadata record. Since it is unclear when exactly da Vinci finished the painting, we represent this uncertainty as two dates of creation: The first day of 1503 and the last day of 1509.

## Using Tidy Metadata Principles for MAPs
Tidy metadata principles start to take on more meaning when we apply them to the types of data curation challenges we face in building schemas, identifying attribute namespaces, and controlling values for *unique* resources. In practically performing data curation we won't always have the advantage of describing resources that have just one best set of attributes or just one standard to appeal to. Often times we will necessarily want to combine different attributes and different standards to create a unique, but standard way of describing a resource. This is, essentially, the gist of a metadata application profile. An application profile allows a specific institution or metadata creator to combine the most appropriate attributes and authority controls for describing resources they manage.

I think of a metadata application profile like a playlist - sometimes it's perfectly reasonable to put on [Fiona Apple's latest](https://en.wikipedia.org/wiki/Fetch_the_Bolt_Cutters) (and you should definitely listen to this album [says Professor Weber]) and take a walk. But, sometimes we want to create a mix of the best individual tracks from different albums for our cross-country drive.

Metadata application profiles combine the best attributes, from different schemas, necessary for accurate description. In practice, this means that we have to create a machine-readable way to define and govern each of the attributes that we include in a metadata application profile. There are generally two approaches to creating a MAP:

**1. Combine attributes from existing schemas**: The most common way to create a MAP is to reuse attribute definitions that have already been published. We can do this, practically, by declaring in our record which attributes we are using from which schemas.

In XML, this might look like the following combination of Dublin Core and the Data Documentation Initiative (DDI) which is used in social sciences:

```
<metadata
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xmlns:dc="http://purl.org/dc/elements/1.1/"
xmlns:ddi="http://ddi:profile:3_1">

<dc:title>Portrait of Lisa Gherardini, wife of Francesco del Giocondo, known as the Mona Lisa</dc:title>
<ddi:language xsitype="ISO639-1"/>English</ddi:language>
<ddi:language xsitype="ISO639-1"/>French</ddi:language>
<ddi:language xsitype="ISO639-1"/>Italian</ddi:language>
```

- In the header of our XML file we referenced two scheams: DDI `xmlns:ddi="http://ddi:profile:3_1"` and Dublin Core `xmlns:dc="http://purl.org/dc/elements/1.1"`
- For the attributes, we used a mix of `dc:title` and `ddi:language` - both are defined by namespaces in our referenced schemas. Why would we want to select a different attribute? In this instance, Dublin Core and DDI differ, slightly, in how they define a language of a resource (here is how DDI defines a [language](https://ddialliance.org/Specification/DDI-Lifecycle/3.2/XMLSchema/FieldLevelDocumentation/schemas/reusable_xsd/elements/Language.html)). If we worked at an institution where we felt that the definition most suited to our descriptive needs was DDI, a MAP gives us a way to combine DDI and Dublin Core. In the readings, I have listed some examples of MAPs that do exactly this. 

One interesting note about MAPs: In some cases it is not only a matter of selecting the best attributes for description, but modifying an attribute set so that it can accurately describe the role that data are playing as evidence in some field. An excellent example of this is the Darwin Core metadata profile - which is used to describe species occurrence records in natural history. [Darwin Core](https://dwc.tdwg.org/terms/) uses numerous attributes defined by Dublin Core (hence the name) but modifies their definition slightly to be interpreted accurately by natural historians. Think for example about the attribute [Creator](https://www.dublincore.org/specifications/dublin-core/dces/) in the Dublin Core attributes - this is defined as "An entity primarily responsible for making the resource". Unless we want to get into a deep philosophical discussion about creationism and the origins of species, this is an attribute definition of a cultural heritage resource that poorly aligns with the needs of a natural historian. To skirt this philosophical dilemma, Darwin Core removes the need for a creator in its MAP, and instead defines concepts like "Occurrence" and "Event of Observation" to better meet the needs of natural historians. 

**2. Publish your own unique attribute namespace**: There may be cases where, after searching existing schemas, there is a need to create a new attribute that can uniquely describe a resource. In this case, the institution that is creating metadata will take on the responsibility of defining and publishing a namespace that defines a unique attribute. For most cases, **creating a unique attribute namespace should be a last resort**. It is difficult to practically sustain a unique published namespace - it requires making sure that the attribute definition remains accessible publicly on the web, and that any machine that attempts to process (or understand) your attribute definition can do so indefinitely. That being said, there are times when this is necessary. 

Here are two examples of institutions that have created unique attribute namespaces: 

- The [Digital Public Library of America (DPLA)](https://dp.la/), which aggregates published digital content from cultural heritage institutions across the United States, has a need to create a unique namespace for attributes of a resource that are aggregated. At DPLA, there will often be multiple copies of or replications of a resource. In trying to provide a canonical resource, DPLA needs a way to describe when one resource has been replaced by another (that is, one copy has been superseded by an original). In this case, DPLA needed to create a unique namespace for the attribute of a resource that had been replaced. So DPLA created the attribute `dpla:isReplacedBy` and `dpla:replaces`. They then published the definition for this attribute to the web so that other machines can accurately interpret what is meant by `dpla:isReplacedBy` and `dpla:replaces`. You can view DPLA's Metadata Application Profile [here](https://pro.dp.la/hubs/metadata-application-profile). 

- <del>[Project Open Data](https://project-open-data.cio.gov/)</del> now [resources.data.gov](https://resources.data.gov/) is an initiative by various US federal agencies to create policies and standards that can guide the accurate publication of government data to the web. Resources.data.gov appears to be working on a schema, but the Project Open Data's [metadata schema](https://project-open-data.cio.gov/v1.1/schema/) is still published (which it should be) and defines various attributes of a government dataset that should be included in any dataset's metadata. This schema is, at its core, a modification of many attributes from the W3C's [Data Catalog Vocabulary (DCAT)](https://www.w3.org/TR/vocab-dcat-2/). For example, the `type` attribute in Project Open Data's schema is simply borrowing from the DCAT namespace (see the definition [here](https://project-open-data.cio.gov/v1.1/schema/#type)). But, Project Open Data also loosely defines a number of attributes in their schema. That is, they are creating unique namespaces and giving directions to data publishers to follow their schema without borrowing from or reusing existing attribute namespaces and definitions. This is, in my view, wildly inefficient but not so uncommon. I offer this as a cautionary tale. Project Open Data has taken on the task of publishing, updating, and sustaining this schema and its unique namespace attributes indefinitely. If, at any time, these namespaces are unavailable then the machines depending upon the unique definitions will not be able to accurately interpret resources described by Project Open Data's schema. I would also note that there has not been broad conformance with this schema across federal agencies - I'll leave commentary about WHY this might be the case up to your imagination.      

## Tidy Metadata Best Practices 
In this module, I have laid out some principles for how metadata *should* be created. These are principles that, in practice, may require modification or may be unnecessary given the time intensive task of describing digital data. 

Metadata is, as we've discussed throughout the quarter, a tradeoff between expressivity and tractability. Throughout this module I am arguing that tractable metadata is that which follows a tidy metadata principle of, where possible, reusing existing schemas, attributes, and controlled vocabularies. This significantly reduces the need to sustain metadata standards, and allows for our metadata records to be broadly accessible to both humans (through a graphic user interface) and machines (through encoding).  

A few other important notes for practicing tidy metadata principles. 

- **Cardinality**: Cardinality refers to constraints on the use of an attribute. Cardinality describes whether an attribute is optional, or mandatory. In creating tidy metadata, we can use cardinality to practically control the number of attributes that are necessary in our metadata records. We can for example create rules that say a number of attributes are possible to include in a record, but are not mandatory. This alleviates metadata creators from having to describe too many attributes of a resource, but also empowers them to, where possible, include these attributes. Cardinality can also apply to value constraints. We can say whether a `Date`, for example, must conform with an ISO standard or whether this is an optional constraint. Cardinality is often exceptionally useful for doing upstream curation where we may want to unburden data collectors from creating too much metadata, and encourage, where possible, their use of a practical standard for doing so. 
- **Where to find namespaces, schemas, and authority control?**: In this chapter, I've broadly advocated for adherence to and reuse of existing attributes and schemas. Practically, these standards are very domain specific. Working in one domain or another requires navigating all of the standards that have been previously developed, and carefully selecting an appropriate standard. Unhelpfully, I will say this gets much easier in practice. But, that generic advice doesn't do much good for the early-career data curator. 
  - To locate existing schemas, and their pre-defined attributes I find the Research Data Alliance (RDA) catalog of metadata standards to be very useful. A front-end browser for this catalog is available [here](https://rdamsc.bath.ac.uk/search) and if you are interested in how this was created, a repository of the issues, discussions, and code is available [here](https://github.com/rd-alliance/metadata-catalog-dev) as well as a paper describing the process [here](https://rd-alliance.org/metadata-principles-and-their-use.html).
  - In the private sector, metadata is an increasingly commodified resource. Many LIS graduates go on to do professional taxonomic work at places like Getty, Amazon, Expedia, etc. The schemas used internally by these companies are often difficult to access - so unfortunately I can't really point to good examples here. However, it is worth seeing how the private sector values and attempts to create paid services around metadata - such as [Octopai](https://www.octopai.com/). 
  - To locate and accurately use authority controls, the task is even harder. In part, because there are so many different types of institutions that promote a way to standardize the value of a metadata attribute. Think, for example, of all the different ways that a date can be expressed. I find two resources helpful when thinking about general value constraints: 1. Marcia Zeng's [description and resource list](https://marciazeng.slis.kent.edu/metadatabasics/working.htm) and 2. This short list from [MiniTex](https://www.minitex.umn.edu/CatMeta/Standards/Value.aspx). As with attributes, many choices in an authority control depend upon what data we are curating, for whom, and during what period of time. I realize that is unsatisfying, but I promise that this gets easier the more that you have to locate and find authorities to constrain a value. Over time, I find myself, when given the choice, selecting the authorities that I trust, and that I prefer (e.g. ISO 639-1 for Languages).

___
<br />  
One parting note - There is a concept which doesn't fit neatly into our discussion of MAPs and Tidy Metadata, but is important to think about when approaching metadata for data curation. I'll try to briefly summarize the idea of a 1:1 principle and unpack why this is important for data curation in the concluding section.  

## Principle: 1:1 Relationships
>The principle whereby related but conceptually different entities, for example a painting and a digital image of the painting, are described by separate metadata records. ([Reference](https://www.dublincore.org/specifications/dublin-core/usageguide/glossary/))  

The one to one (1:1) principle holds that metadata records should correspond to one, and only one entity (or instance) of a class ([Hillmann](https://www.dublincore.org/specifications/dublin-core/usageguide/2005-08-15/), 2005, sec. 1.2). This principle was first articulated in the context of cultural heritage metadata where related, but conceptually different instances are often difficult to interpret.

The canonical example of the 1:1 principle is a photograph of the Mona Lisa, and the actual painting of the Mona Lisa by Leonardo Da Vinci. If we search for all of the records that describe the Mona Lisa we can find numerous metadata records about the Mona Lisa with the creator Leonardo da Vinci. [Here](https://www.europeana.eu/en/search?page=1&view=grid&query=Mona%20Lisa) are the results from searching for "Mona Lisa" in the Europeana database which aggregates metadata across European cultural heritage institutes. If we actually look closely at these records - we will find multiple examples of the creator being named as "Leonardo da Vinci". 

But, this surely isn't the case. There is one and only one instance of a painting by Leonardo da Vinci named Mona Lisa. If following the 1:1 principle, there should be one and only one record that claims the creator of Mona Lisa is Leonardo da Vinci. All other instances are replications, or different instantiations (e.g. photographs, trinkets, t-shirts, etc) of the original painting that were created by someone other than Leonardo da Vinci.  

In his [doctoral thesis](https://alliance-primo.hosted.exlibrisgroup.com/permalink/f/lvbsh/TN_cdi_proquest_journals_1415842856), Richard Urban empirically examined violations of the 1:1 principle (2012). He found that metadata creators, from professional catalogers to those untrained in knowledge organization, applied this principle unevenly. The result is a broad confusion about what items a cultural heritage institution actually holds, and which are replications or secondary sources. 

At its core, the 1:1 principle is trying to disentangle the complex relationship between digital objects and their various manifestations. In data curation, we often need to adhere to this principle when we are describing complex datasets that contain multiple tables, multiple versions of a table, or multiple instances of the same data. To practically do this, we can follow a few basic rules: 

1. Recognize item-level and collection-level relationships: Item-level and collection-level metadata is meant to provide a way for individual objects (data) to be described in a part/whole relationship. Collection level metadata is often about describing attributes of the aggregate of a set of resources, rather than any one resource specifically. But, these relationships may be hard to disentangle upon first glance. The first step I take when dealing with complex relationships like this is to try to specify the *autonomy* of the data being described. Does it make sense as a stand-alone dataset that can be accurately interpreted, or does it have a relationship with additional resources that are needed for meaningful reuse. If the latter is the case, then there is a need to create a collection level description. 
2. Classes and instances (this is very similar to item-level and collection-level descriptions): When approaching a dataset or table, often we need to determine what class this instance of data belongs to. Remember our Homer, Lisa and Bart Simpson example from the [Tables, Trees, & Triples](https://norlab.github.io/LIS-546-SPR2021/content/tables-trees-triples.html) module? We have instances (characters) of the class (Simpson family). The membership in the class is defined by attributes such as having a parent that is named Simpson. In adhering to 1:1 principle we should create metadata that can represent these relationships without violating the idea that one record corresponds with one instance. That is, we can create a description of a class (Simpsons) and instances of the class (characters), but we should not be creating a Simpson family record if it contains only one character description. Instead - we can use the collection-item level descriptions to accommodate this relationship. We could, for example create a record that describes all Simpsons, and then individual records for each character. We might also nest these attributes, such that only our Collection-level metadata records describes the instances of the class (members). In Dublin Core we can use attributes like `is_part_of` to define these types of collection-item level relationships (read more [here](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#http://purl.org/dc/terms/isPartOf)).
3. Reuse existing records: Just as we should take care to reuse existing namespaces and schemas following tidy metadata principles, we might also attempt to reuse *parts* of existing metadata records that already exist. For example, if we were describing a photo of a the Mona Lisa we should be able to find existing records describing the painting, and existing records describing photos of original art works. We can then attempt to create a unique record of our photo of the Mona Lisa by reusing these existing schemas, namespaces, and attribute-value pairs. In this search for related items - we can further establish whether we are creating a unique record, or whether we are describing a unique resource for the first time. The former, finding and discovering related records, is useful if and only if the data we are curating is likely to exist in multiple places. This is a useful technique for downstream curation, but is of limited value to upstream curators.  

**Referenced works** 

- Hillmann, D. (2005). [Using Dublin Core, Dublin Core Metadata Initiative](https://www.dublincore.org/specifications/dublin-core/usageguide/2005-08-15/) (DCMI).
- Wickham, H. (2014). [Tidy data](https://www.jstatsoft.org/article/view/v059i10/v59i10.pdf). Journal of Statistical Software, 59(10), 1-23. 
- Urban, R. J. (2012). [Principle paradigms: revisiting the Dublin Core 1:1 principle](https://alliance-primo.hosted.exlibrisgroup.com/permalink/f/lvbsh/TN_cdi_proquest_journals_1415842856) (Doctoral dissertation, University of Illinois at Urbana-Champaign). 

## Lecture

<iframe width=853 height=473 frameborder="0" scrolling="no" src="https://screencast-o-matic.com/embed?sc=cYhi29gDkq&v=6&ff=1&title=0&controls=1" allowfullscreen="true"></iframe>

## Reading

Application profiles:

- Heery, R., & Patel, M. (2000). [Application profiles: mixing and matching metadata schemas](http://www.ariadne.ac.uk/issue/25/app-profiles/). Ariadne, (25).  

- [The Singapore Framework for Application Profiles](https://www.dublincore.org/specifications/dublin-core/singapore-framework/). Note this is currently under revision by DCMI. You can catch up on their work [here](https://github.com/dcmi/dcap) (and also see an example of `use cases` in the wild)

Some examples of metadata application profiles:

- [DPLA](https://pro.dp.la/hubs/metadata-application-profile)
- [Cornell Library](https://confluence.cornell.edu/display/mwgweb/CUL+Metadata+Application+Profiles)
- [Carnegie Hall Archives](https://carnegiehall.github.io/digitalcolls-metadataprofile/)

Relevant (optional) readings:

- Hebron, T. K. (2018). [Extending and Adapting Metadata Audit Tools for Mountain West Digital Library Members](https://journal.code4lib.org/articles/13632 ) Code4Lib Journal, (41). 
- Curado Malta, M., Bermúdez Sabel, H., Baptista, A. A., & González-Blanco García, E. (2018). [Validation of a metadata application profile domain model](http://e-spacio.uned.es/fez/view/bibliuned:363-Egonzalez15). 
- 
Case Study for discussion (optional):

- Stein, A., & Dunham, E. (2018). [Meaningful Data Sharing: Developing the Illinois Data Bank Metadata Framework](https://www.ideals.illinois.edu/handle/2142/103173). Journal of Library Metadata, 18(2), 59-83. 

<h2><a id="Exercise">Exercise</a></h2>
The exercise for this week is to work on your protocol, and in particular the [Metadata Application Profile Assignment](https://norlab.github.io/LIS-546-SPR2021/assignments/07_assignment_metadata). Your readings this week describe metadata application profiles in detail. 
