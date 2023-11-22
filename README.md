# Replication Package For Paper: Enhancing Change Impact Prediction by Integrating Evolutionary Coupling with Software Change Relationships

**IMPER** is a change <u>**I**</u>mpact <u>**P**</u>rediction method that integrates <u>**E**</u>volutionary coupling with software change <u>**R**</u>elationships. The approach consists of following four main steps:

+ **Step 1: Relevant Transaction Filtering**. Filtering the relevant transaction set based on the given query $Q$. 
+ **Step 2: Association Rule Generation**. Generating association rules and obtaining the impact candidate set.
+ **Step 3: Spatial-Temporal Window Processing**. Considering the temporal and spatial change relationships to obtain the impact candidate set.
+ **Step 4: Candidates Integrating and Ranking**. Making a union of these two sets to find the final impact set.

This repo provides the replication package for the paper. Due to the huge size of the dataset, it has been uploaded to a cloud storage service for easier access and distribution. (Baidu Netdisk: the [links](https://pan.baidu.com/s/1cwpj4-OMM5mOXhOdgWrV1Q ) , and the password：xgwo). It includes the following folders:

* **code**:  the tool for our study, including: 1) Generating qualified queries; 2) Change prediction query by query with four approach, i.e., ROSE, TARMAQ, IMPER, IMPER-ST; 3) Evaluation. This tool output evaluation results for every query and the average metrics (MAP, Precison, Recall and F1-score).  
* **git_repo**: the git repository used in this study. 
* **neo4j_dataset**: the neo4j dataset contains entity-level software relationship graphs and change information (changed classes, changed member methods, changed member variablea and changed files) from over 19,003 versions of six well-maintained projects. 
* **code_entiy_genealogy**: the data for code entity genealogy.

Users are suggested to refer to the research paper for more detials. 

This project is still in an early stage of development, and we are improving the implementation and documentation. Please feel free to contact ******(author) for the replication package.

## Environment

- java 11+
- neo4j 4.2 (https://neo4j.com/download-center/#community)
- memory 64G+

## Quick start
To conduct our study, follow the next steps.  Note that only one project can be analyzed at a time.

**Step 1: Setup the database**

Please copy the related database to the folder `data` (in the root path of Neo4j database), copy the plugins into  `plugin` and use Neo4j 4.2 to open the database.  

**Step 2:  Configure the application-dev.yml**
Configure the application-dev.yml under the folder `code` by setting your own configuration. (<u>If you're using the existing database, just configure the database address, username, and password.</u>)

**Step 3:  Run imper-study**

Command: `java -jar imper-study.jar -imp -config ./application-dev.yml -rd /home/zdh/code_rec -pj commons-io -fi commons-io_file(Map)_1031.txt -mi commons-io_functionInfo(Map).txt -tw 35 -mc 20 -od /home/zdh/code_rec`

- -imp : use to run IMPER
- -config: the path of `application-dev.yml`
- -rd: the root path of the mapping results, e.g., `/home/zdh/code_rec`
- -pj: the project name, e.g., `commons-io`
- -fi: the code entiy genealogy (file), e.g., `commons-io_file(Map)_1031.txt` (e.g., the absolute path is `/home/zdh/code_rec/commons-io/commons-io_file(Map)_1031.txt`)
- -mi: the code entiy genealogy (method), e.g., `commons-io_functionInfo(Map).txt`
- -tw: the time window (half)
- -mc: the max commit size in the time window
- -od: the output root path (the evaluation results, MAP, Precison, Recall and F1-score) (e.g., `/home/zdh/code_rec`)


