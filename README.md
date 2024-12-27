# MongoDB vs. Neo4j for Biomedical Data

This repository contains the code and thesis for my Master's project comparing the performance of MongoDB and Neo4j for managing and querying biomedical data.

## Project Overview

The goal of this project was to evaluate the strengths and weaknesses of MongoDB and Neo4j, two popular NoSQL databases, when applied to a real-world biomedical dataset. The analysis focused on key performance indicators such as query speed, indexing efficiency, and memory consumption across various data retrieval tasks.

## Key Findings

*   Neo4j: Excels in handling complex relationships and graph traversals, making it suitable for tasks involving interconnected data, such as biological pathways or drug interaction networks.
*   MongoDB: Demonstrated advantages in terms of overall query speed and schema flexibility, particularly for simpler queries and document-oriented data.

## Data Used

The analysis was conducted using a biomedical dataset 

Dataset -

https://explore.data.humancellatlas.org/projects/05657a59-9f9d-4bb9-b77b-24be13aa5cea

About -

The dataset provides a comprehensive analysis of fibroblast heterogeneity in human skin, uncovering significant insights into the complexity of fibroblast populations. Through a combination of spatial transcriptional profiling of human and mouse dermis and single-cell transcriptional profiling of human dermal fibroblasts, the study identifies at least four distinct fibroblast populations in adult human skin. Key findings include:

Distinct Fibroblast Populations: The identification of at least four unique fibroblast subpopulations, each characterized by specific markers that allow for their prospective isolation.

Marker Expression and Functionality: Although these markers are rapidly lost when fibroblasts are cultured, the different subpopulations maintain distinct functionalities. This includes variations in Wnt signaling, communication with T cells, and their ability to support human epidermal reconstitution in organotypic culture.

Spatial Distribution: The study reveals that while some fibroblast subpopulations are spatially segregated within the dermis, others are not.

Implications for Wound Healing and Fibrosis: These findings highlight the role of distinct fibroblast subpopulations in normal wound healing processes and in diseases characterized by excessive fibrosis. The research suggests potential therapeutic applications, such as the ex vivo expansion or in vivo ablation of specific fibroblast subpopulations.

*Publication - *

Spatial and single-cell transcriptional profiling identifies functionally distinct human dermal fibroblast subpopulations

## Running the Code

## Databases Configuration  
## MongoDB Connection Setup  
To perform the analysis with MongoDB, the very first thing to do was to launch a MongoDB instance on MongoDB Atlas which is a fully managed service that helps in the deployment and scaling of databases on the cloud. Then the creation of the MongoDB Atlas account was done. After the creation of the account, there was a need to set the network access, and I chose the “Access from Anywhere” option. This made it possible for the database to be accessed from any given IP address and it was very convenient especially where data analysis is done in the cloud. As the next step, I set up a free cluster on MongoDB Atlas network environment. In MongoDB, a cluster is a group of databases which are spread over different physical machines to achieve the purpose of failover and increase the availability of the databases. The free cluster was an economical way of solving this problem and at the same time had all the necessary tools and functions for the analysis of the given data.  
  
In this cluster, a database with the name ‘HumanDermalFibroblastSubpopulations’ was created to contain the dataset records. In this database, a collection also with the same name is also present. To this end, HumanDermalFibroblastSubpopulations was created to help in the management of the data. MongoDB used databases and collections which are like tables of relational databases to store the data in a more structured way, and this made the data retrieval and manipulation easier.  
Further, to link the Python environment with MongoDB, I employed the MongoDB. The Atlas interface to create a connection string. Upon clicking on the “Connect” button in the MongoDB Atlas dashboard, I choose the language of my choice to be Python and then the driver version to be 3. 12 or later. This created a connection URI that contained all the information that was needed for the connection to the database for instance the username, the password and the cluster address. The connection was then created in the Python environment by using the pymongo library that is used in connecting with MongoDB databases in Python. When the connection is made, I had to check whether the target collection in the MongoDB contains data or not and if it does, I deleted all the data before starting with the insertion of new data. This was to avoid the introduction of the new dataset into an environment that may still contain some data that could in one way, or another influence the results, or the performance metrics being evaluated. This configuration made it possible to make a correct and consistent comparison of the performance of MongoDB when dealing with the biomedical dataset.  
  
## Neo4j Connection Setup  
For Neo4j the connection setup involved the creation of an account on Neo4j AuraDB, which is a cloud-based graph database service that is fully managed. Others like Neo4j excel in handling data with high relational density, for example the relationships between the different cells or genes in biomedical data. After that, I claimed a free instance in the Neo4j AuraDB platform. This instance, named as ‘instances1’, was considered as the database environment for this study. At the setup level, Neo4j offered a downloadable configuration file that included the information on how to connect to the database that included the URL, the username, and the password. It was important to secure the connection to the Neo4j database and to authenticate it when accessing it from a Python environment.  
To make the connection, I employed the neo4j Python library as it is designed for working with 
Neo4j databases. The information given in the configuration file was used to log in into the Neo4j instance and establish a session. This session provided for the actual writing of Cypher queries, which is the query language of Neo4j for creating, reading, updating, and deleting data in the graph database.  
Before loading the new dataset to Neo4j, I first had to clean the database to remove any prior data that could be related to the new dataset. I looked for important fields like gene and removed any previous data that could be a conflict with the new dataset. This was crucial to avoid any form of contamination that could in turn affect the performance metrics that were being recorded and which were to be used to determine how well Neo4j would perform with the new dataset.  


## Thesis

The full Master's thesis document providing a detailed analysis .
