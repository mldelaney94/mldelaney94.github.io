---
author: matthew delaney
---

We've been dealing with the theory of database design this week. There is one particular topic called closures, which deals with the number of relationships necessary to model our database.

When designing databases, we want to have as little redundancy as possible. The easiest tradeoff to make in databases is space for performance, however by understanding the relationships in the database well, we can understand how to get from info A to info Z without having to create new tables.

#What makes a good schema?

The simple answer is a minimal amount of redundancy. Of course, some redundancy can lead to performance increases, but that's the definition we're working with for now. 

A slight twist on this answer can be 'for any update or insertion or deletion, we want to affect as little of the current information as possible'. For instance, if we have a monolithic table that contains data across a multitude of businesses, any time a business changes address, every reference to it in that table must be updated. If we had a table that contained all businesses that could link to other tables, we may only need to update that address once. As well, if a mistake is introduced at some point in the table, it can be hard to know which entry is correct. For a deletion, deleting a line may make it impossible to recover some data unique to that line. For instance a business that exists in one row of the table but is not the primary key. If that key (say, an account) ceases to exist, it is possible that we want that business to exist in our records.

#Dependency

Table r(R):

A  |  B  |  C  |  D  |  E 
a<sub>1</sub>  |  b<sub>1</sub>  |  c<sub>1</sub>  |  d<sub>1</sub>  |  e<sub>1</sub>  | 
a<sub>2</sub>  |  b<sub>1</sub>  |  c<sub>2</sub>  |  d<sub>2</sub>  |  e<sub>1</sub>  |
a<sub>3</sub>  |  b<sub>2</sub>  |  c<sub>1</sub>  |  d<sub>1</sub>  |  e<sub>1</sub>  |
a<sub>4</sub>  |  b<sub>2</sub>  |  c<sub>2</sub>  |  d<sub>2</sub>  |  e<sub>1</sub>  |
a<sub>5</sub>  |  b<sub>3</sub>  |  c<sub>3</sub>  |  d<sub>1</sub>  |  e<sub>1</sub>  |

There is a definition here that will inform the rest of this section called functional dependency, which is a type of relationship between two attributes in a table.

We say that a dependency X -> Y exists if:

* for any t, u in r, t[X] = u[X] implies t[Y] = u[Y]

Basically if two tuples agree in value for the set of attributes X, they must agree for their set of attributes Y. In this case we could say that 'Y is functionally dependent on X'.

So now we will use this definition to find some dependencies in the above table.
