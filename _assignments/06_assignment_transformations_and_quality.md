---
type: assignment
date: 2021-03-30T4:00:00+4:30
title: 'Transformations and Quality Assignment'
pdf: /static_files/assignments/asg.pdf
attachment: /static_files/assignments/asg.zip
solutions: /static_files/assignments/asg_solutions.pdf
due_event: 
    type: due
    date: 2021-04-04T23:59:00+3:30
    description: 'Transformations and Quality Assignment due'
---
## Assignment: Data Transformations and Quality Criteria

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

