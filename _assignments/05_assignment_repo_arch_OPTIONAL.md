---
type: assignment
date: 2021-05-02T23:59:00Z
title: 'Repository Architectures (OPTIONAL) Assignment'
pdf:
attachment:
solutions:
due_event: 
    type: due
    date: 2021-05-09T23:59:00Z
    description: 'Repository Architectures (OPTIONAL) Assignment due'
---
## Assignment OPTIONAL: Repository Architectures
Most of us will never design a new data curation system from the ground up. We will, by and large, develop on top of existing software platforms that provide basic features. This means we can focus our time and attention on **configuring** these architectures to meet our specific needs.  

There are many existing open-source data repositories from which we can choose. However, deciding between different repository platforms can be a daunting task. We have to balance time, skills, user needs, and the requirements for both hardware and other related software.

In this exercise we'll try to use some basic criteria to profile the software underlying a repository platform, and then decide which repository we feel might ultimately be best for our data collections.

Side note - many of you will not need to evaluate a repository for the sake of your protocol, but this is a handy skill to practice so may still be worth your time.  

For this exercise you can chose between four repository platforms.

1. [CKAN](https://ckan.org/) - by the Open Knowledge Foundation [Demo](http://demo.ckan.org/)
2. [Dataverse](http://dataverse.org/) - by Harvard University [Demo](https://demo.dataverse.org/) (see in particular this [introduction](http://guides.dataverse.org/en/latest/installation/intro.html#intended-audience)
3. [Samavera]( https://samvera.org/samvera-open-source-repository-framework/technology-stack/) - by a consortium of University Libraries and Cultural Heritage Institutions
4. [Fedora](https://wiki.duraspace.org/display/FF) - by the DuraSpace consortium.

**Evaluation criteria**       
In order to evaluate a repository we need clear criteria about what makes one more suitable to our users' needs than any other.

Here is an example of a profile I created for the [Qualitative Data Repository](https://docs.google.com/document/d/1_wB4SUWwsZYcYq87k4_GfFxL9pPYXDqFsTGwhXhriQY/edit) when our advisory board needed a simple explanation of why the technical team would invest a year of time and money into switching from one repository software platform (Fedora) to another (Dataverse).

In general we can evaluate a repository in two ways:

1. Profiling the software that underlies a repository system: The underlying software for a repository can be thought of as the "repository architecture" (and is sometimes colloquially called the "repository stack"). An architecture typically consists of all the different components that are needed to realize the repository. An architecture typically includes an operating system, a server application, a database, a search engine, and a set of protocols that allow for data to be transferred between different components of the architecture. For example - the list below is the Dataverse architecture:

- Linux: RHEL/CentOS is highly recommended since all development and QA happens on this distribution.
- Glassfish: a Java EE application server to which the Dataverse application (war file) is to be deployed.
- PostgreSQL: a relational database.
- Solr: a search engine. A Dataverse-specific schema is provided.
- SMTP server: for sending mail for password resets and other notifications.
- Persistent identifier service: DOI and Handle support are provided. Production use requires a registered DOI or Handle.net authority.

2. Creating user stories / use cases to understand what expectations our users might have about a repository. We have previous completed exercises on these more "user centered" techniques - so for now we will focus our time and attention on evaluating the underlying software of a repository.  

In choosing a repository platform we should try to find the right balance between software (and our own skills) and user needs (or how well the software meets those needs).

**Profile**

Here is a template you can use when starting to evaluate a new repository platform:

*Platform-Name*

- Who are the producers of the repository?
- What is the license of the repository's software?  
- What are the hardware requirements of the repository?
- What are the related software requirements of the repository (in other words - what is its architecture)?  
- What is the current release or version number that is available for download?
- - How often are releases made available?
- - How do repository developers report an error or bug found in a release?
- How many people are using the repository? What kinds of data do they curate?
- How is the software modified by those users? (e.g. are there plugins or extensible libraries?)
- What type of data is typically stored in the repository? Does the architecture afford any special features for particular kinds of data (e.g. geospatial data repository software might have a map plugin)
- How customizable is the metadata for the repository? Can new application profiles be easily created and implemented?
- Is the repository interoperable with other types of repositories? (e.g. Does the repository have an easily accessible API?)

**Major Strengths:**

**Major weaknesses:**

**Overall Assessment:**

