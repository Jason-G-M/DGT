## Introduction

### Dependency Graph Tool

Dependency Graph Tool (DGT) is designed to analyze and display the overall information of APIs' compatibility for .Net Core of different processes/builds in Substrate assemblies.

The main functionalities of the tool contain:
1. Management 
- View the number of compatible and incompatible assemblies. (e.g. Repo and NuGet compatibility.)
- Track the progress of adapting incompatible assemblies to compatible ones.

2. Analysis
- Analyze the level relationship of assemblies/types. (e.g. paths from a process to an assembly, or paths from one assembly to another.)

3. Monitoring
- Monitor the trend of changes in dependencies. 
- Detect the changes in the dependencies of assemblies and the dependency tree.


### Architecture

DGT service consists of four processes and is supported by two databases.

#### Processes
- Scan Tool
1. Scan assemblies' information.
-Build Graph Tool
1. Build dependency graphs and import them to the Neo4j database.
2. Analyze relationships between assemblies.
- Web API
1. Querry data from databases.
2. Delivery data to the front end.
- Front End
1. Present data.

#### Databases
- SQL DB
Store configuration
- Neo4j
Store graph data
