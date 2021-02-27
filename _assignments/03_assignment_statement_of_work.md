## Assignment 0: Project definition, scope, and audience
Your first assignment will be to write a group definition and statement of work. This should include the following elements:

- Group name
- Group members
- The topic of your curation protocol (e.g. transportation data)
- The target audience for your protocol (e.g. who would use or consult your protocol)
- Write a three to five sentence statement about your collective goals for the protocol (e.g. what do you want to work on and learn about through the activity)
- Provide a link to any relevant data sources you have identified.

## Assignment 1: User Stories + Use Cases
Throughout class we will read examples data curation work that are "user centered." Two broad techniques for developing requirements of systems that are "human centered" are through use cases, and user stories. The following exercises may be helpful in the work you plan to do this quarter in building a protocol to satisfy a community of data users.

### User Stories
User stories are a simple, but powerful way to capture requirements when doing systems analysis and development.

The level of detail, and the specific narrative style will vary greatly on the intended audience. For example, if we want to create a user story for accessing data stored in our repository we will need to think closely about different types of users, their skills, the ways they could access data, the different data they may want, etc.

This could become a very complicated user story that could be overwhelming to translate into actionable policy or features of our data repository.

Instead of trying to think through each complicated aspect of a user's need we can try to atomize a user experience. In doing so we come up with simple story about the user that tells us the "who what and why" - so that we can figure out "how" ...

*Elements*

The three most basic elements of a user story are:
- Stakeholder - the type of stakeholder might be a user, curators, administrator, etc.
- Feature - this could be a feature of a dataset, a system, or service
- Goal - what is the stakeholder trying to achieve with the feature?

*Templates*
A template for a user story goes something like this:

As a `user` I want `some feature` so that I can achieve some `goal`.

As a `data user of the QDR` I want to `find all datasets about recycling for cities in Pacific Northwest` So that I can reliably `compare recycling program policies and outcomes` for this region.

Some variations on this theme: More recent work in human centered design places the goals first - that is, it attempts to say what is trying to be done, before even saying who is trying to do it...

This is helpful for thinking about goals that may be shared across different user or stakeholder types.

This variation of a user story goes something like:

In order to achieve some business value
As a stakeholder type
I want some new system feature

*Here is your task*

Create user stories that help you understand the potential wants, needs, and desires of your designated community of users. For this first attempt - focus on user stories around data sharing.  How might you satisfy these user stories? What choices do these stories help clarify or obscure about your protocol, and your designated community?

Here is an example that can help clarify the way that user stories are assembled for the protocol: https://rochellelundy.gitbooks.io/r3-recycling-repository/content/r3Recycling/protocolReport/userCommunity.html


### Use Cases (Best Practices)
Another way to begin gathering information about users and their expectations for data are through use cases. As you read in week 5 for class the W3C has developed a template for conducting use cases for data on the web best practices. This exercise asks you to use that template to investigate best practices for data and repositories that are relevant to your quarter protocols.

The simple steps to follow:
- Read the Data on the Web Use Cases & Requirements (as part of your weekly reading) https://www.w3.org/TR/dwbp-ucr
- Identify a data collection published on the web that is relevant to your protocol.
- Develop a Use Case following the DWBP outline.

**Protocol Deliverable**
Your should begin with a brief 3-5 sentence overview of the data, publisher, and the relevance to your quarter project. Additionally, your report might include the following:

- Elements that characterize the data available (or at least published in summary form) on the web: Domains served by the data; Obligation / Motivation for publishing the data; Potential ways that the domains will use the data; Quality (this will vary – we’ll discuss in class); Lineage (provenance); Size; Type / Format; Rate of Change; Lifespan; Potential audiences.
- Positive aspects of the published data.
- Negative aspects of the published data.
- Challenges that will face data publishers, users, or meeting best practices over time. See: https://www.w3.org/TR/dwbp-ucr/#general-challenges
- Requirements for DWBP: Select two requirements for your data source, and justify why this is a requirement (~3 sentences) (See: https://www.w3.org/TR/dwbp-ucr/#requirements-1

## Assignment 2: Data Collection Policies

**Intro**        
Most data repositories draw a distinction between self-deposit, submission-based, and opportunistic data collecting.

- Self-deposit is exactly what it sounds like - data producers or collectors upload their data directly to a repository. Curation takes place post-hoc to make sure that there are no viruses, that data are within copyright protections, etc (Typical curation tasks like cleaning of data, creation of additional metadata, structuring of data, etc, are not typically applied to these kinds of collections.)
- Submission repositories require users to propose a deposit and follow strict guidelines before their data is accepted. Curators in this role act as a gatekeeper for what comes into the repository, and also perform preliminary work that will lead to more useful data over the long-term.
- Opportunistic is also exactly what it sounds like - data curators serve as the collectors of data and thus are expected to both evaluate as well as prepare the data for eventual deposit into a long-term storage repository.

Regardless of how data are acquired there should be clear criteria for which kinds or types of content are relevant to a repository, and which are not. This criteria might also include the size, formats, and even subjects of a data collection. Libraries and Archives have historically referred to these kinds of policies as collection development. Data collections (or data repositories) differ in terms of their collection policies in that they are concerned with not only what types of data should be collected, but also what form and with what additional relevant resources should data be accepted. In short, a data collection policy brings together the readings and lecture we did around data cleaning, packaging, and sharing.

Here are some valuable examples:        

  - ICPSR: [What should my deposit include?](http://www.icpsr.umich.edu/icpsrweb/deposit/)
  - Cornell: [Content collection policy](http://guides.library.cornell.edu/ecommons/contentpolicy) and also see their valuable [Recommended file formats](http://guides.library.cornell.edu/ecommons/formats)
  - QDR - has a very structured submission process, including a set of helpful [data deposit forms](https://qdr.syr.edu/deposit/process)
  - IDEALS - a repository at the University of Illinois has an excellent policy on the preservation grantees they can make for [particular file formats](https://wiki.illinois.edu/wiki/display/IDEALS/Digital+Preservation+Support+Policy#DigitalPreservationSupportPolicy-Category1)
- SF Open Data [Submission Guidelines](https://datasf.org/publishing/submission-guidelines/)
- A more general approach is to define the scope of an open data program, see the Seattle Open Data [description](http://www.seattle.gov/tech/initiatives/open-data/about-the-open-data-program) for a helpful example. 

**Protocol Deliverable**      
Establish the policies that will govern your data collection policy. This should include (at minimum):

- What are the criteria that make a dataset, or collection, relevant to your protocol? What, if anything, might exclude a relevant dataset?
- What will you require to be included for a minimum viable package of data? (e.g. the data must have a clear license, a format that is (or can be converted to) an open standard, and enough contextual documentation that structured metadata can be created).
- What formats will you accep, and what formats will not you accept?
- How big can a collection be (in size)?
- What kind of preservation guarantees will you make for each format?

You should feel free to LIBERALLY borrow from existing repository policies or protocols that we have looked at this quarter. You should also feel empowered to look at other protocols, or other repositories and decide how to answer some of these questions.

## Assignment 3: Data Transformations and Quality Criteria

In previous exercises we created a policy that specified what kind of data our repository should collect, from whom we would accept data deposits, as well as practical expectations about the size and formats we preferred to collect when collecting new data. In this activity we are going to establish policies for what we do with collected or deposited data.

**Transfer**        
In an ideal scenario there is a clear transfer of ownership when data, documentation, and related resources are exchanged between one individual and another. But, often data are acquired, collected, or discovered in less than ideal scenarios. As data curators, we want to set up some general expectations about how data *should* be packaged or prepared for us to take-over responsibility for its preservation and reuse. Some general questions to consider when developing a data transfer policy:    

- How will users or curators upload data to your repository? What kind of authenticity checks would you perform to make sure this data is what it purports to be? Does this include any virus scanning tools? (hint: CKAN provides some easy answers to this)
- How will you identify confidential, sensitive, or private information contained in this data? (in other words, What constitutes private or sensitive information?O What is your policy for removing / redacting / protecting this kind of content?
- How will you apply an identifier to each data collection? What kind? Why?
- What additional metadata (beyond what the depositor provides) should be created at the point of data being transfered to your stewardship?
- Is there any additional documentation that should be created in order to meaningfully preserve or use this data?

**Transformation**      
Taking ownership (or stewardship) of a data collection may be just the first step in an extended workflow of preparing the data for being ingested by a repository, stored for long term preservation, or prepared for discovery and meaningful reuse in a data catalog.

Of course, transforming data to meet the needs of our users is one of the primary (and most time consuming) activities in data curation. The time we spend doing this is a direct function of the perceived value we have for the data we are curating. That means that we should try to establish policies that are appropriate for the sensitivity, uniqueness, and value of the data we are transforming. Consider the following questions as you begin to write out a policy about how data should be transformed for your protocol. Think about writing this section in the spirit of our previous reading on ['How to share data with a statistician'](https://github.com/jtleek/datasharing).

*File / Format*    
- In what formats should the data be stored? Does this differ from how it should be served to end-users? If so, how might you describe the policy for transforming data from one format to another (e.g. when you will create a CSV from a set of tables in a database)
- Will you accept data that are stored in proprietary formats? How will you communicate this to users?
- How will you record, store, and provide end-users information about what changes you've made to a dataset? (e.g. When you migrate file formats, or update the data you could then change the version of the dataset from 1.0 to 2.0? Conversely, you could have an "updated_last" field in your metadata, etc.)

*Data Values*           
- What steps should be taken to normalize the data? (hint: You could go through something like `common transforms` in Refine and come up with an easy (and exhaustive) template). Consider common transformations like: consistent column (variable) names, developing a data dictionary for each dataset, standardizing values for missing or null values, labeling values (by type - e.g. text, number, boolean, categorical, etc.)
- Return to the principles of Tidy Data (e.g. Each variable you measure should be in one column; Each different observation of that variable should be in a different row; There should be one table for each "kind" of variable; and, If you have multiple tables, they should include a column in the table that allows them to be joined or merged). How would you help ensure that these principles are met for data that you collect?

## Assignment 4: Data Licensing

**Licenses**      
Open data requires a declaration that the information objects (as provided by an individual or institution) are free for consumption, reuse, and/ or repurposing. Licenses further allow us to protect data creators and data stewards by being explicit about the expectations we have for how data should be used, repurposed, etc.

There are a number of licenses available - each allowing you to achieve different protections for data creators or data stewards.

Below are a small set of resources that describe data licenses and how to make choices between licenses:
- Project Open Data's commentary on [open licenses for open data](https://project-open-data.cio.gov/open-licenses/)
- Cornell Library's [IP rights for data management](https://data.research.cornell.edu/content/intellectual-property) (See in particular their distinction between databases and data)
- [Data.World's guide to open licenses](https://help.data.world/hc/en-us/articles/115006114287-Common-license-types-for-datasets)

**Implications for your protocol**

Here are the basic questions you should answer in this section of your protocol:
- What licenses will you attach to a dataset, and why? (If your data is already under a license you might explain that here)
- Will you make any exceptions?

If you are interested in a primer on data licensing you might consult the following:
- Carroll, M. W. (2015). Sharing research data and intellectual property law: A primer. PLoS biology, 13(8), e1002235. [HTML](https://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.1002235)

## Assignment 5: Metadata Application Profiles

Overall goal: Looking at the relevant examples from our [metadata folder](https://github.com/OpenDataLiteracy/LIS-598-DataCuration2-Sp2019/tree/master/Metadata-Examples), and the use cases you developed last week, begin to develop an application profile for your project.

To complete this exercise, you will need to answer the following questions:
- What elements are necessary to meet your stakeholders' expectations?
- Will an existing schema meet all of these requirements?
- If not what extensions or modifications are needed?
- How does this align with the repository software (CKAN) that you have chosen.

How do I evaluate metadata standards useful for my project? Dian Hillman offers these criteria:

- Look at what others in the domain are using (done!)   
– Stability/volatility of the standard (and whether it really IS a standard) (i.e. How often is the standard changed?)
– How well does the community for the standard integrates new needs and ideas
– Startup and maintenance costs for use in an individual project (higher for more complex formats and implementations)
- What is (at most basic level) required for an application profile?

For each element in your application profile you should (eventually) provide the following:
- Namespace, and namespace definition
- Status: Mandatory or optional
- Permitted encoding scheme for values
- Any rules for content
- An example

Here is an example entry from a previous class: https://github.com/RochelleLundy/INFX-551-Spring2017/tree/master/r3Recycling/protocolReport/metadata

You should also choose an encoding scheme for your examples (JSON or XML. Note: I don't expect you to actually produce these records.)

Remember from our readings: "If an implementor wishes to create 'new' elements that do not exist elsewhere then (under this model) they must create their own namespace schema, and take responsibility for 'declaring' and maintaining that schema." You probably don't want to do this, but if you do let's discuss the requirements.

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

