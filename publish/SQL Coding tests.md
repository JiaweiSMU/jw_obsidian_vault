### Histogram Pattern
A histogram maps **values → frequency of occurrence**. 
- Count **per item occurrence** first (e.g. user posted how many tweets), then **count how many items share the same count.**
	1. Group by item, then count
	2. Group by the count of the item
### Relational Division Problem
Such questions are usually in this format - "Find all X that are associated with all of a given set of Y"
- Example questions include
	- Find **customers** who bought **all** products in a bundle
	- Find **students** who passed **all** required courses
	- Find **employees** who completed **all** mandatory trainings
	- Find **suppliers** who stock **all** parts needed for a product
- Usually the table will have a Identifier column (e.g. User) and things that are associated with the user. There are usually duplicate identifier within the table
To solve such a question
1. Making use of **IN**, **GROUP BY** & **HAVING + COUNT**
	1. skills in ('stuff we are searching for') -> Group by Identifier -> Having count() - Depends on how many they must match
2. Using **SELF-JOINS** 
	1. select a.id from table a 
		   join table b on a.id = b.id and skill = 2
		   join table c on a.id = c.id and skill = 3
		where a.skill = 1 (**This must be at the end can't put at the start**)


