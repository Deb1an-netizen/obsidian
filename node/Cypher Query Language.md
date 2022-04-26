Cypher Query Language is a SQL like query language that is used to retrive data from Graph. 
**Main components:** 
1. [[Nodes]] - the entities or objects in the Graph Data Model
2. [[Relationships]] - connection between nodes
3. [[Labels]] - a grouping semantic for nodes
4. [[Properties]] - Key-Value pair attributes, stored on nodes and relationships

Cypher is a declarative graph query language that allows for expressive and efficient [querying, updating and administering](https://neo4j.com/docs/cypher-manual/current/introduction/quering-updating-administering/) of the graph. It is designed to be suitable for both developers and operations professionals. Cypher is designed to be simple, yet powerful; highly complicated database queries can be easily expressed, enabling you to focus on your domain, instead of getting lost in database access.

Cypher is inspired by a number of different approaches and builds on established practices for expressive querying. Many of the keywords, such as `WHERE` and `ORDER BY`, are inspired by [SQL](http://en.wikipedia.org/wiki/SQL). Pattern matching borrows expression approaches from [SPARQL](http://en.wikipedia.org/wiki/SPARQL). Some of the list semantics are borrowed from languages such as Haskell and Python. Cypher’s constructs, based on English prose and neat iconography, make queries easy, both to write and to read.

**Structure**

Cypher borrows its structure from SQL — queries are built up using various clauses.

Clauses are chained together, and they feed intermediate result sets between each other. For example, the matching variables from one `MATCH` clause will be the context that the next clause exists in.

The query language is comprised of several distinct clauses. These are discussed in more detail in the chapter on [Clauses](https://neo4j.com/docs/cypher-manual/current/clauses/).

The following are a few examples of clauses used to read from the graph:

-   `MATCH`: The graph pattern to match. This is the most common way to get data from the graph.
    
-   `WHERE`: Not a clause in its own right, but rather part of `MATCH`, `OPTIONAL MATCH` and `WITH`. Adds constraints to a pattern, or filters the intermediate result passing through `WITH`.
    
-   `RETURN`: What to return.
    

Let’s see `MATCH` and `RETURN` in action.

Let’s create a simple example graph with the following query:

```
CREATE (john:Person {name: 'John'})
CREATE (joe:Person {name: 'Joe'})
CREATE (steve:Person {name: 'Steve'})
CREATE (sara:Person {name: 'Sara'})
CREATE (maria:Person {name: 'Maria'})
CREATE (john)-[:FRIEND]->(joe)-[:FRIEND]->(steve)
CREATE (john)-[:FRIEND]->(sara)-[:FRIEND]->(maria)
```

