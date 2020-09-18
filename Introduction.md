## Introduction

### Dependency Graph Tool
Dependency Graph Tool (DGT) is designed to analyze and display the overall information of APIs' compatibility for .Net Core of different processes/builds in Substrate assemblies.

The main functionalities of the tool contain:
- Management 
1. View the number of compatible and incompatible assemblies. (e.g. Repo and NuGet compatibility.)
2. Track the progress of adapting incompatible assemblies to compatible ones.
- Analysis
1. Analyze the level relationship of assemblies/types. (e.g. paths from a process to an assembly, or paths from one assembly to another.)
- Monitoring
1. Monitor the trend of changes in dependencies. 
2. Detect the changes in the dependencies of assemblies and the dependency tree.

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
1. Store configuration
- Neo4j
1. Store graph data


## Startup
The Dependency Graph Tool (DGT) depends on SQL Server, Neo4j, JRE, .Net Core 3.1, Node.js, npm packages, and API Port. Please finish the installation and configuration before starting the DGT.

### Neo4j

#### Neo4j Installation
Visit the official website and download [Windows Neo4j Community Edition 3.5.21](https://neo4j.com/download-thanks/?edition=community&release=3.5.21&flavour=winzip&_ga=2.176909797.114973728.1598256184-1237716368.1595239954&_gac=1.195112414.1595902492.CjwKCAjw9vn4BRBaEiwAh0muDCf_xYI1PeoiFtSlHOCWO_yWQkg7QwJMjmjo0Rm-wYihI7v0nc2QMhoCSBMQAvD_BwE).

#### Neo4j Configuration
##### Run Neo4j
###### Run as a Windows Service
Open Command Prompt and direct into Neo4j 3.5.21 file path.
1. Install service, use:
```markdown
bin\neo4j install-service
```
2. Change memory configuration, use: (Note: Set heap.max_size according to your device's memory.)
```markdown
echo dbms.memory.heap.initial_size=8g >> conf\neo4j.conf
echo dbms.memory.heap.max_size=16g >> conf\neo4j.conf
```

3. Start service, use:
```markdown
bin\neo4j start
```
###### Run as a Console Application
Try this method if Neo4j cannot start as a windows service.
Run Neo4j as a console application, use:
```markdown
bin\neo4j console
```
##### Set Neo4j Username and Password
1. Visit the login page of Neo4j. Find the address on the console prompt, for example, http://localhost:7474/.
2. Choose Authentication type as Username / Password, enter neo4j for both username and password to initialize the account.
3. Enter a new password. 
4. Connect Neo4j.
##### Neo4j Host
Neo4j Host can be found after logging in, for example, the Neo4j Host in the figure below is bolt://127.0.0.1:7687.
![Neo4j dashboard and Neo4j Host](image/Neo4jDashboardAndHost.png)

### SQL Server
### JRE
### NetCore 3.1
### Node.js
### npm
### API Port

## DGT configuration
### Folder configuration
### Script configuration
### UI configuration
### Recurring job configuration


## Deployment
### Assembly package demo
### Start with a script

## Operation Manual
### Dashboard
### Tools
#### Process's Root Parents
#### Process to Assembly Path
#### Assembly to Assembly Path
#### Process's Assemblies
#### Assembly Details
#### Difference
#### New Assembly Check
#### Assembly Children Paths

### Type Analysis
#### Process's Types
#### One Shortest Path Process to Type
#### One Shortest Path From Assembly to Type
#### Multi-Path Process to Type
#### Multi-Path Assembly to Type


### System
#### Process Config
#### Repo Config
#### Import Status
#### Error Log

