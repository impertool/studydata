# studydata
# Replication Package For Paper: Enhancing Change Impact Prediction by Integrating Evolutionary Coupling with Software Change Relationships

**IMPER** is a change <u>**I**</u>mpact <u>**P**</u>rediction method that integrates <u>**E**</u>volutionary coupling with software change <u>**R**</u>elationships. The approach consists of following four main steps:

+ **Step 1: Relevant Transaction Filtering**. Filtering the relevant transaction set based on the given query $Q$. 
+ **Step 2: Association Rule Generation**. Generating association rules and obtaining the impact candidate set.
+ **Step 3: Spatial-Temporal Window Processing**. Considering the temporal and spatial change relationships to obtain the impact candidate set.
+ **Step 4: Candidates Integrating and Ranking**. Making a union of these two sets to find the final impact set.

Users are suggested to refer to the research paper for more detials. Please feel free to contact ******(author) for the replication package.

This project is still in an early stage of development, and we are improving the implementation and documentation. 

This repo provides the replication package for the paper (Baidu Netdisk: the [links](https://pan.baidu.com/s/1cwpj4-OMM5mOXhOdgWrV1Q ) , and the password：xgwo). It includes the following folders:

* **code**:  the tool IMPER.  
* **git_repo**: the git repository used in this study. 
* **neo4j_dataset**: the neo4j dataset contains entity-level software relationship graphs and change information from over 19,003 versions of six well-maintained projects. 
* **code_entiy_genealogy**: the data for code entity genealogy.
* **manual_study**: the manual validation data. 

## Environment

- java 11+
- neo4j 4.2 (https://neo4j.com/download-center/#community)
- python 3.8+
- memory 64G+ 


