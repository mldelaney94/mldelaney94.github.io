---
author: matthew delaney
---

We've been dealing with the theory of database design this week. There is one particular topic called closures, which deals with the number of relationships necessary to model our database.

When designing databases, we want to have as little redundancy as possible. The easiest tradeoff to make in databases is space for performance, however by understanding the relationships in the database well, we can understand how to get from info A to info Z without having to create new tables.

# What makes a good schema?

The simple answer is a minimal amount of redundancy. Of course, some redundancy can lead to performance increases, but that's the definition we're working with for now. 

A slight twist on this answer can be 'for any update or insertion or deletion, we want to affect as little of the current information as possible'. For instance, if we have a monolithic table that contains data across a multitude of businesses, any time a business changes address, every reference to it in that table must be updated. If we had a table that contained all businesses that could link to other tables, we may only need to update that address once. As well, if a mistake is introduced at some point in the table, it can be hard to know which entry is correct. For a deletion, deleting a line may make it impossible to recover some data unique to that line. For instance a business that exists in one row of the table but is not the primary key. If that key (say, an account) ceases to exist, it is possible that we want that business to exist in our records.

## Dependency

Table r(R):

A  |  B  |  C  |  D  |  E 
a<sub>1</sub>  |  b<sub>1</sub>  |  c<sub>1</sub>  |  d<sub>1</sub>  |  e<sub>1</sub>  | 
a<sub>2</sub>  |  b<sub>1</sub>  |  c<sub>2</sub>  |  d<sub>2</sub>  |  e<sub>1</sub>  |
a<sub>3</sub>  |  b<sub>2</sub>  |  c<sub>1</sub>  |  d<sub>1</sub>  |  e<sub>1</sub>  |
a<sub>4</sub>  |  b<sub>2</sub>  |  c<sub>2</sub>  |  d<sub>2</sub>  |  e<sub>1</sub>  |
a<sub>5</sub>  |  b<sub>3</sub>  |  c<sub>3</sub>  |  d<sub>1</sub>  |  e<sub>1</sub>  |

There is a definition here that will inform the rest of this section called functional dependency, which is a type of relationship between two attributes in a table.

We say that a dependency X  ->  Y exists if:

* for any t, u in r, t[X] = u[X] implies t[Y] = u[Y]

Basically if two tuples agree in value for the set of attributes X, they must agree for their set of attributes Y. In this case we could say that 'Y is functionally dependent on X'.

So now we will use this definition to find some dependencies in the above table:

1. A is unique for each row. So with the right A we can get any piece of info in that row. So A -> B, A -> C etc.

2. All E values are the same. So A -> E, B -> E, C -> E etc.

3. We can summarise what information we can get from a column like this A -> BCDE, meaning that with A you can get any or all of BCDE.

4. But #3 can be confusing. ABCD -> E is not valid. Why? Because we want to know the minimum amount of information necessary to get some other piece of information. So ABCD -> E would be valid if you needed each of ABCD to access E's value. 

## Deriving functional dependencies

We now want to be able to generalise some ideas about functional dependencies. To find out their properties. The basic motivation of this is that some dependencies suggest the existence of other dependencies.

For instance are dependencies reflexive I.E. X -> X? Well just go back to the definition to see that this is trivially true.

Augmentation: X -> Y => XZ -> YZ (2)

Transivity X -> Y, Y -> Z => X -> Z (3)

Additivity X -> Y, X -> Z => X -> YZ (4)

Projectivity X -> YZ=> X -> Y, X -> Z (5)

Pseudotransitivity X -> Y, YZ -> W => XZ -> W (6)

So now lets go through an exercise:

Determine validity of AB -> GH given:
		R = ABCDEFGHIJ

	F = { AB -> E, AG -> J, BE -> I, E -> G, GI -> H }

	So we need to get AB -> GH from this.

	Well we know 	AB -> E (given)
	FROM E -> G	AB -> G (given)
	Great, we have one half, we need AB -> H to solve by additivity
	FROM AB -> AB 	AB -> B (Projectivity 5)
	FROM AB -> E, AB -> B AB -> BE (addivity)
	FROM BE -> I	AB -> I
	FROM AB -> G	AB -> GI (additivity)
	FROM GI -> H	AB -> H
	FROM AB -> G	AB -> GH (additivity)

So using these rules we can find other functional dependencies in the table.

## Closures

So now we know what a functional dependency is, we want to define this term **closure** and figure out its use/motivation.

If we have a set X of functional dependencies (FD's), how many new FD's can we derive as above? Well whatever the answer, the largest collection of FD's possible from X is called F^+ and is called the closure of F.

Closures allow us to answer two interesting questions:

* Is a particular dependency X -> Y derivable from F?
* Are two sets of dependencies F and G equivalent?

For the former, compute F^+ and see if X -> Y is part of that set
From the latter, compute F^+ and G^+ and see if they are equivalent. So obviously they're minorly useless as its as slow as computing a powerset of a largish set.

So then how are we supposed to use closures with functional dependencies? The answer is, you don't. Instead you use the set of attributes rather than fd's. Attributes are the X and Y in X -> Y. Basically we compute the largest set of attributes from X getting X^+, if some subset of attributes Y are in X^+ then X -> Y is in F^+.
