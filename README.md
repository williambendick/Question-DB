# Question DB
This is the database repo for an application I am developing called Question. 

## Question Application 
Question is a diagnostic tool and symptom tracker. It’s 2 main functions are:
1. Manage and document the process of problem solving.
2. Log and aggregate data about the symptoms of problems.

Go to [Question Application UI](#question-application-ui) section to see how data is used in the application.

Question is a [Local-first](https://www.inkandswitch.com/local-first/) application.


## Question DB Schema

Question DB is a relational database that uses an [EAV data model](https://en.wikipedia.org/wiki/Entity%E2%80%93attribute%E2%80%93value_model). Data is organized in a hierarchy of nodes where each node belongs to a particular type. 

![image](https://raw.githubusercontent.com/williambendick/Question-DB/refs/heads/main/Images/erd.png)

Projects, Types, Nodes, and Instances are the fundamental entities of the schema:

| Entity | Purpose/Description |
|---|---|
| Projects | Organize and separate data. Each project contains its own unique Types.|
| Types | Define classes that Nodes can be assigned to.|
| Nodes | The central datapoints used in the Question application. Each Node contains 1 primary datapoint, and may contain 1 or more secondary datapoints. Nodes are organized hierarchically within a project: each Node has either a top-level position, or is a descendant of another Node.  |
| Instances | Represent occurrences of certain kinds of Nodes. Each Instance contains 1 primary datapoint, and may contain 1 or more secondary datapoints.|

Additional entities:

| Entity | Purpose/Description |
|---|---|
| Type List Items | Define values that can be used for the primary datapoints of Nodes.|
| Fields | Define attributes for the secondary datapoints of Nodes.|
| Field List Items | Define values that can be used for the secondary datapoints of Nodes.|
| Field Sub List Items | Define Field List Items that are subsets of other Field List Items.|
| Node Data | Store the values of a Node's secondary datapoints (Fields).|
| Instance Fields | Define attributes for the secondary datapoints of Instances.|
| Instance List Items | Define values that can be used for the secondary datapoints of Instances. |
| Instance Sub List Items | Define Instance List Items that are subsets of other Instance List Items.|
| Instance Data | Store the values of an Instance's secondary datapoints (Instance Fields).|

Go to [Detailed ER Diagram](#question-application-ui) section.

## Question DB Scripts

Table Creation  
Data Population  
Queries  

## Database File
This SQLite database contained in a single file (link)

## Question Application UI

 Each data point in Question is assigned to a type such as 'Subject' or 'Description', and that data gets displayed in the UI as a tree:

![image](https://github.com/williambendick/Question-DB/assets/41596014/070c9cf4-fafb-42bb-b05c-09b8c3554b7d)

![image](https://github.com/williambendick/Question-DB/assets/41596014/b4a785af-b145-406d-a090-cbc925581dd0)

Return to Question Application section
