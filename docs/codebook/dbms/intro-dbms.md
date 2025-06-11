# Introduction of Database Management Systems
## Database Management System
DBMS contain information about a particular enterprise.

- collection of interrelated data.
- set of program to access the data.
- An environment that is both convenient & efficient to use

**Application:** Banking, Airlines, Universities, Sales, Online Retailers, Manufacturing, Human Resource and more..

***Database is very large.*** 

### Drawback of using *file system*
- Data **Redundancy** and **inconsistency**.
- Multiple file formats, duplication of information in different files.
- difficulty in accessing data.
- Data isolation.
- concurrent access by multiple user
- **security** problems.

## Database and Data
Database is a ***collection*** of **related data**, and 
Data is ***collection of facts & figures*** that can be processed to produce information.

## What is DBMS
A database management system stores data in such a way that it became easier to ***retrieve, manipulate & produce information***.

#### Characteristics
- Real World Entity.
- Relation-based tables.
- Isolation of data & application.
- Less redundancy & consistency.
- ***ACID*** Properties - Atomicity, Consistency, Isolation and Durability.

## Level of Abstraction
low to high ⬇️
- **Physically Level** -  Describe how a data is stored.
- **Logical Level** - Describe data stored in database & the relationship among the data.

```
type instructor = record
ID: string;
name: string;
dept_name: string;
salary: integer;
```

- **View Level** - Application program hide details of ***data types*** for security purpose.

#### View of Data
An Architecture for a database system.

```
View Level ⬇️ -- view1, view2, view3, ...

Logical Level

Physical Level
 
```
## Schema and Instance
Similar to types and variable in programming language

### Schema
- **Logical Schema** - The overall logical structure of the database. Analogous to type information of a variable in program

```sql
# example - customer schema

 Name | customer ID |Account # | Aadhaar ID | MObile Number |
```

- **Physical Schema** - The overall physical structure of the database. physical means *actual*.

### Instance
The ***actual content*** of the database at a **particular point in time**.
Analogous to the value of a variable.

```sql
# example - customer schema

 Name | customer ID |Account # | Aadhaar ID  -- schema
 Pavan Laha | 6725 | 917322 | 182719289372  -- instance
```

**Physical Data Independence**: The ability to modify the *physical schema* without changing the *logical schema*.

- Analogous to independence of 'Interface' & 'Implementation' in object-oriented systems
-  Applications depend on a logical schema

## Data Models
A collection of tools for describing - ***data, data relationship, data semantics & data constraints***.

### Some of Data Models
- ***Relational Model***
- Entity-Relationship Data Model
- Object based Data Model (object-orient & object)
- Semi structured Data Model (XML)

### Relational Model
All the data is stored in *various tables*.

#### Data Definition Language (DDL)
Specification notation for *defining the data schema*.

```sql
# example

CREATE TABLE instructor (
ID char(5),
name varchar(20),
dept_name varchar(20),
salary numeric(8,2)
)
```

- DDL complier generates a set of table template stored in a *data dictionary*. (-- data dictionary Metadata(data about data))
- Database Schema.
- Integrity constraints. (-- *Primary Key- ID uniquely identifies instructors*)
- Authorization. (-- who can access what)

#### Data Manipulation Language (DML)
Language for ***accessing and manipulating the data*** organized by the appropriate data model

> Data Manipulation Language also known as **query language**

#### Two Classes of Language
**Pure**: Used for proving properties about computational power and for optimization. (-- *relational algebra*)

**Commercial**: Used in commercial system.
-- *SQL(Structure Query Language)*, XML(Extensible Markup Language)

*The process of designing the general structure of the database*.
- Logical Design
- Physical Design

### Methodology to ensure that each of the relation in data in 'good'.

### Entity-Relational Model
Model an enterprise as a collection of entities and relationship 
represented by an ***entity-relationship diagram***.

### Normalization Theory
formalize what designs are bad, and test for them

### Object Relational Models
Extend the relational data model by including object-orientation and constructs to deal with added data type.
- provide upward compatibility with existing relational language.

### XML
- defined by *www consortium*.
- Originally intended as a document markup language not a database language.
- great way to **exchange data(import/export)**.

## Database Engine
- **Storage Manager**: It is program that provide the interface between ***view level data***.
	- interaction with the OS file manager.
	- Efficient storing and updating of data.

- **Query Processing**:
	- parsing and translation
	- Optimization
	- Evaluation

<!-- diagram -- [[data-engine diagram]] -->

- cost difference between a good and a bad way of evaluating a query can be enormous.
- estimate the cost operation.

*Alternative way of evaluating*:
- equivalent expression
- different Algorithm for each operation.

- **Transaction Management**:
	- what if the system fails?
	- what if more than one user is concurrently updating the same data?

	A **Transaction** is collection of operational that perform a *single logical function* in a database application.

	**Transaction Management** component ensure that the database remain in a consistent(correct) state despite *system failure*(power failure and operating system crashes) and *transaction failure*.

## Database User and Administrator
**Users**: The people who use the system are called users. 
Users can be categorized into those who actually use and manage the material (referred to as "Actors on the Scene") and those who make it possible to create the database and the DBMS software (referred to as "Workers Behind the Scene").

**Administrators**: One of the main reasons to use DBMS is to have centralized control over both the data and the programs that access the data. The person in charge of the system as a whole is termed the database administrator (DBA).

<!-- diagram -- [[database user and administrators]] -->

## Data Architecture
Data Architecture is greatly influenced by the underlying computer system on which the database is running
- centralized
- client-server
- Parallel (Multi-Processor)
- Distributed

## History of Database System
- 1950s to 1960s - database processing using the magnetic tapes for storage
- 1970s - hard disk allowed direct access the data
- 1980s - SQL become industrial standard
- 1990s - Large Multi Terabyte data warehouse
- 2000s - XML and X-Query Standard, Automated database administration
- Now - giant data storage systems like; *google bigtable, yahoo PNuts, Amazon*.
