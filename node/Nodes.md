![[Pasted image 20220426144325.png]]
Nodes are the data entities in graph and it can often be identified by finding the nouns or objects in the data model.

To depict nodes in Cypher it is surrounded with parentheses, e.g. (node).

##### Node Variable:
A node can be later refered by a given variable like (p) for person or (t) for thing. More expressive variable names like (person) or (thing) are used in real world queries.

If the node is not relevant to a result we can specify an anonymous node using empty parentheses (). This means that you will not be able to return this node later in the query.

##### Node Labels"
Labels are kind of like tags that allows us to specify certain types of entities to look for or create.

The concept of label is similar to SQL table name.

###### Nodes in Cypher:
`//data stored with this direction
`CREATE (p:Person)-[:LIKES]->(t:Technology)

``//query relationship backwards will not return results
`MATCH (p:Person)<-[:LIKES]-(t:Technology)
``
``//better to query with undirected relationship unless sure `of direction
`MATCH (p:Person)-[:LIKES]-(t:Technology)
