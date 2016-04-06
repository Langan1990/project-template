# Irish Constituencies Neo4j Database
###### Keith Langan, G00318481

## Introduction
This project is about the 2016 general elections. We have to create all the constituencies and candidates as nodes in neo4j and create relationships between them. 
Then we have to come up with 3 queries that show some useful information about the databsae. 

## Database
I started the database by creating the constituencies. Here is an example of one of the create statements:

	CREATE(constituency:Constituency {id: 4, Name: "Louth", SeatsAvailable: 5})
	
I used the following statement to create the candidates:

	CREATE(can:Candidate {cid: 1, Name: "Pat 'The Cope' Gallagher", Party: "Fianna Fail", Gender: "Male", Age: 67, Constituency: "Donegal", Elected: "Yes"})
	
	

## Queries
Summarise your three queries here.
Then explain them one by one in the following sections.

#### Query one title
This query retreives the Bacon number of an actor...
```cypher
MATCH
	(Bacon)
RETURN
	Bacon;
```

#### Query two title
This query retreives the Bacon number of an actor...
```cypher
MATCH
	(Bacon)
RETURN
	Bacon;
```

#### Query three title
This query retreives the Bacon number of an actor...
```cypher
MATCH
	(Bacon)
RETURN
	Bacon;
```

## References
1. [Neo4J website](http://neo4j.com/), the website of the Neo4j database.
2. (https://www.youtube.com/watch?v=0fKg7e37bQE/),  Github Tutorial
http://irishpoliticalmaps.blogspot.ie/2012/06/constituency-commission-boundary.html
