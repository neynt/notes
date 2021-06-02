# CS 348 textbook notes

## Week 1 (Chapter 1)

- Four data models:
  - Relational model: Tables
  - Entity-relationship model: Things and relationships
  - Object-based model: Objects and methods 
  - Semistructured model: Heterogeneous document store

- Three database languages:
  - DML: Data manipulation language: Insertion and retrieval
  - DDL: Data definition language: Schema, consistency constraints

- Types of integrity constraints:
  - Domain constraint (type)
  - Referential integrity (relationships must be between things that exist)
  - Assertions (general conditions)
  - Authorization (user can read, insert, update, delete)

- Parts of a database system
  - Storage manager: Interface between low-ldevel data and query processor, basically
  - Query processor: Compiles and executes DDL and DML.

- Parts of the query processor
  - DDL interpreter
  - DML compiler
    - Query optimizer
  - Query evaluation engine

- Good shit
  - Atomicity: All or none. Cannot be broken down.
  - Consistency: Makes sense.
  - Durability: Changes live on.

- Types of database users
  - Naïve users: Non-tech
  - Application programmers: Coders
  - Sophisticated users: DBAs
  - Specialized users: S U P E R S

- DBA tasks
  - Define schema
  - Define storage structure and access method
  - Modify schema and physical organization
  - Grant authorization
  - Routine maintenance

## Week 2 (Chapter 2.1, 2.2, 2.3, 2.4, 6.3)

- Table bits
  - **Table**: Columns and rows
  - **Relation**: Table
  - **Tuple**: Row
  - **Attribute**: Column
  - **Domain**: Permitted values for an attribute
  - **Atomic** domain: All elements of the domain are indivisible.
- **Null**: Special value for unknown or nonexistent values.
- **Database schema**: Logical design of database
- **Database instance**: Actual database at a point in time
- **Relation schema**: Assigns each attribute a domains
- Keys
  - **Superkey**: Set of attributes that uniquely identifies tuple
  - **Candidate key**: Minimal superkey
  - **Primary key**: Selected candidate key
  - **Foreign key**: From referencing relation to referenced relation.
- Schema diagram: Diagrams showing tables we've been given in assignments

- The domain relational calculus
  - You know this from A1

## Week 3 (Chapter 3)

- SQL is a thing with things
- Know these Power Words, in rough order
  - SELECT, FROM
    - WHERE
    - AND, OR, NOT
    - NATURAL JOIN: Based on common column names (!)
    - x AS y
    - SELECT DISTINCT
    - LIKE
    - ORDER BY, DESC, ASC
    - UNION, INTERSECT, EXCEPT
    - NULL 
    - AVG, MIN, MAX, SUM, COUNT, DISTINCT
    - GROUP BY
    - HAVING
  - WITH x AS
  - INSERT INTO x VALUES, UPDATE, DELETE FROM

## Week 4 (Chapter 4)

- More conjurations:
  - LEFT OUTER JOIN
  - RIGHT OUTER JOIN
  - FULL OUTER JOIN
  - CREATE VIEW v AS query;
- Transactions:
  - COMMIT WORK
  - ROLLBACK WORK
  - BEGIN ATOMIC ... END
- Integrity constraints:
  - CREATE TABLE, ALTER TABLE
  - NOT NULL
  - UNIQUE
  - CHECK( predicate )
- Referential integrity / triggers:
  - ON DELETE CASCADE
  - ON UPDATE CASCADE
- Complex:
  - CREATE ASSERTION name CHECK predicate

## Week 5 (Chapter 5.1, 5.2, 5.3)

- Dynamic SQL: Construct SQL queries at runtime with functions
- Embedded SQL: Embed SQL directly into the language with preprocessor
- Trigger: CREATE TRIGGER dname AFTER INSERT ON thing REFERENCING NEW ROW AS thing
- Recursive queries: Ok this is actually cool stuff. Table of iteration numbers and tuples.

- No relational algebra lol

## Week 7 (Chapter 7)

- Conceptual design: Intelligently designed
- Logical design: Conceptual schema to database system model
- Physical design: Index structures and stuff
- Entity-relationship models are things. Boxes, circles, diamonds, weak and strong, know 'em. Nobody agrees on how exactly to draw them (are attributes circles or just in the box?)

## Week 8 (Chapter 8.1, 8.2, 8.3, 8.4, 8.5)

- 8.1.
  - Functional dependency: A -> B means there's a FUNCTION from A to B
  - Lossy decomposition: Loses information.
  - Lossless decomposition: Doesn't.
- 8.2.
  - Atomic domain's elements are "indivisible units".
  - 1NF: First normal form. All attributes of R have atomic domain.
- 8.3.
  - Boyce-Codd Normal Form: some crazy complicated normal form
  - 3NF: Third normal form. WtFFFF
- 8.4.
  - m-muh pseudotransitivity though
- 8.5.
  - Learn some decomposition algorithms after the midterm won'tcha
