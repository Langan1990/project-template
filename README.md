# Irish Constituencies Neo4j Database
###### Keith Langan, G00318481

## Introduction
This project is about the 2016 general elections. We have to create all the constituencies and candidates as nodes in neo4j and create relationships between them. 
Then we have to come up with 3 queries that show some useful information about the databsae. 

## Database
I started the database by creating the constituencies. Here is an example of one of the create statements:
	
	```
	CREATE(constituency:Constituency {id: 4, Name: "Louth", SeatsAvailable: 5})
	```
	
I used the following statement to create the candidates:
	
	```
	CREATE(can:Candidate {cid: 1, Name: "Pat 'The Cope' Gallagher", Party: "Fianna Fail", Gender: "Male", Age: 67, Constituency: "Donegal", Elected: "Yes"})
	```
	
This is the statement that created the relationships from candidates to the constituencies
	
	```
	match (a{Constituency:"Clare"}),(b{Name:"Clare"}) create (a)-[r:RAN_IN]->(b) return a,b	
	```
	
## Queries
The 3 quereis i decided to do were. Find all male cadidates in mayo, constituencies with 5 available seats and candidates that were elected in connacht

#### Male Candidates in Mayo 
This query retreives the male candidates who ran in Mayo
```cypher
MATCH (n:Candidate) WHERE n.Gender="Male" AND n.Constituency="Mayo" return n;
```

#### Constituency's with 5 available seats
This query retreives the constituencies who have 5 seats available 
```cypher
MATCH (n:Constituency) WHERE n.SeatsAvailable = 5 return n;
```

#### Candidates Elected in Connacht
This query retrieves all the elected candidates in constituencies in Connacht
```cypher
MATCH (n:Candidate) WHERE n.Constituency="Mayo" AND n.Elected="Yes" OR n.Constituency="Galway East" AND n.Elected="Yes" OR n.Constituency="Galway West" AND n.Elected="Yes" OR n.Constituency="Roscommon-Galway" AND n.Elected="Yes" OR n.Constituency="Sligo-Leitrim" AND n.Elected="Yes"  return n;
```

## References
1. [Neo4J website](http://neo4j.com/), the website of the Neo4j database.
2. (https://www.youtube.com/watch?v=0fKg7e37bQE/),  Github Tutorial
http://irishpoliticalmaps.blogspot.ie/2012/06/constituency-commission-boundary.html

http://www.thejournal.ie/election-2016/constituency/6/
