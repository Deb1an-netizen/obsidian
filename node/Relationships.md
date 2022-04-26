![[Pasted image 20220426145342.png]]
To fully utilize the power of a graph database relationships between [[Nodes]] are used. Relationships are represented in Cypher using an arrow --> or <-- between two nodes. Additional information, such as how nodes are connected(relationship type) and any properties pertaining to the relationship, can be placd in square brackets inside of the arrow.

`//data stored with this direction
`CREATE (p:Person)-[:LIKES]->(t:Technology)

``//query relationship backwards will not return results
`MATCH (p:Person)<-[:LIKES]-(t:Technology)

``//better to query with undirected relationship unless sure of direction
`MATCH (p:Person)-[:LIKES]-(t:Technology)`

##### Relationship Types:
Relationship types categorize and add meaning to a relationship, similar to how labels group [[Nodes]].

Relationships can be usually identified using verbs and actions.
For example:
-   `[:LIKES]` - makes sense when we put nodes on either side of the relationship (Jennifer LIKES Graphs)
    
-   `[:IS_FRIENDS_WITH]` - makes sense when we put nodes with it (Jennifer IS_FRIENDS_WITH Michael)
    
-   `[:WORKS_FOR]` - makes sense with nodes (Jennifer WORKS_FOR Neo4j)

##### Relationship Variables:
Just as in [[Nodes]] if we want to refer a relationship later in a query we can give it a variable like [r] or [rel]. We can also use longer more expressive variable names like [likes] and [knows]. If there need not to be any refreneces for a relationship later then it can be specified as an anonymous relationship using two dashes --,-->,<--.
