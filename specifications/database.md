
[Specifications](../../specifications.md)
===

Model definition
---

### Conception

#### Entity Relation Diagram

As a first draft of what the data model could look like, there is an ERD to help to visualize relations between data in the model.

![Database ERD](./assets/graph/DB-ERD.svg)

#### Postgres types

In concern to bring more explanations about types used in Postgres, here come an link index.

- [uuid](https://www.postgresql.org/docs/9.5/static/datatype-uuid.html)
- [text](https://www.postgresql.org/docs/9.5/static/datatype-character.html)
- [int](https://www.postgresql.org/docs/9.5/static/datatype-numeric.html#DATATYPE-INT)
- [array](https://www.postgresql.org/docs/9.5/static/arrays.html)
- [bool](https://www.postgresql.org/docs/9.5/static/datatype-boolean.html)
- [inet](https://www.postgresql.org/docs/9.5/static/datatype-net-types.html#DATATYPE-INET)
- [macaddr](https://www.postgresql.org/docs/9.5/static/datatype-net-types.html#DATATYPE-MACADDR)
- [timestamp](https://www.postgresql.org/docs/9.5/static/datatype-datetime.html)

### Statements

#### Universal Unique IDentifiers

Sequential ids (serial, auto-increments) are forbidden in matlo systems nowadays for security reasons ad using uuids prevent from brut-force attackers.

#### Common fields

In most of the tables in the model, there will be some common fields for audit or facility purpose.

##### created_at

Almost every resources managed in the model are created at some time. Those resources tables will have a `created_at` datetime field to store the creation time.

##### created_by

Almost every resources managed in the model are created by someone. Those resources tables will have a `created_by` field storing user primary key. The `created_by` should not be a foreign key as the user could be deleted but we need to conserve the relation and maintaining this index would slow down all the `INSERT/UPDATE` statements.
