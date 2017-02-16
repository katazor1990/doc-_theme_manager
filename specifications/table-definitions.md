
[Specifications](../../specifications.md)
===

### tables definition

- ![Primary key](./assets/key.svg) defines a primary key
- ![Unique](./assets/fingerprint.svg) defines a unique index
- ![Foreign key](./assets/link.svg) defines a foreign key
- ![nullable](./assets/null.svg) defines a nullable field

#### UserRoles

This table can not be named "Roles" after the ERD because this term is reserved by Postgres.
Its content will not be updated by the interface.

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | r_id | uuid | uuid_generatev4() |
| ![Unique](./assets/fingerprint.svg) | name | text |  |
|  | level | int |  |

#### UserProfiles

This table can not be named "Users" after the ERD because this term is reserved by Postgres.
It is the main database performance issuer as it is used to log in users.

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | u_id | uuid | uuid_generatev4() |
| ![Foreign key](./assets/link.svg) | role | uuid |  |
|  | firstname | text |  |
|  | lastname | text |  |
| ![Unique](./assets/fingerprint.svg) | email | text |  |
| ![nullable](./assets/null.svg) | phone | text | NULL |
|  | password | text |  |
|  | created_at | timestamp |  |
|  | created_by | uuid |  |

##### Foreign keys

- `role` field of this table links to the `r_id` field of `UserRole`.

#### Instances

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | i_id | uuid | uuid_generatev4() |
| ![Unique](./assets/fingerprint.svg) | name | text |  |
|  | description | text |  |
|  | created_at | timestampz | now() |
|  | created_by | uuid |  |
| ![nullable](./assets/null.svg) | sync_at | timestampz | NULL |
| ![nullable](./assets/null.svg) | sync_by | uuid | NULL |

***

#### Nodes

Represent configuration of each nodes, physical or virtual, of matlo instances.

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | n_id | uuid | uuid_generatev4() |
| ![Foreign key](./assets/link.svg) | instance | uuid |  |
|  | virtual | bool |  |
| ![Unique](./assets/fingerprint.svg) | hostname | text |  |
| ![Unique](./assets/fingerprint.svg) | ip | inet |  |
| ![nullable](./assets/null.svg)![Unique](./assets/fingerprint.svg) | mac | macaddr | NULL |
|  | cpu | int |  |
|  | memory | int |  |
| ![nullable](./assets/null.svg) | host | text | NULL |
|  | created_at | timestampz | now() |
|  | created_by | uuid |  |
| ![nullable](./assets/null.svg) | sync_at | timestampz | NULL |
| ![nullable](./assets/null.svg) | sync_by | uuid | NULL |

##### Foreign keys

- `instance` field of this table links to the `i_id` field of `Instances`.

#### Services

List the services (PG, ES, backend, frontend, ...) that could be installed on nodes.
Its content will not be updated by the interface.

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | s_id | uuid | uuid_generatev4() |
|  | name | text |  |
|  | category | text |  |

#### Node Service

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | ns_id | uuid | uuid_generatev4() |
| ![Foreign key](./assets/link.svg) | node | uuid |  |
| ![Foreign key](./assets/link.svg) | service | uuid |  |
|  | created_at | timestampz | now() |
|  | created_by | uuid |  |
| ![nullable](./assets/null.svg) | sync_at | timestampz | NULL |
| ![nullable](./assets/null.svg) | sync_by | uuid | NULL |

##### Foreign keys

- `node` field of this table links to the `n_id` field of `Nodes`.
- `service` field of this table links to the `s_id` field of `Services`.

***

#### Respositories

List source repositories to deploy on instances.
Its content will not be updated by the interface.

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | r_id | uuid | uuid_generatev4() |
| ![Unique](./assets/fingerprint.svg) | name | text |  |
|  | organization | text |  |
| ![Unique](./assets/fingerprint.svg) | url | text |  |

#### Versions

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | v_id | uuid | uuid_generatev4() |
| ![Foreign key](./assets/link.svg) | repo | uuid |  |
| ![Foreign key](./assets/link.svg) | instance | uuid |  |
|  | ref | text |  |
|  | created_at | timestampz | now() |
|  | created_by | uuid |  |
| ![nullable](./assets/null.svg) | sync_at | timestampz | NULL |
| ![nullable](./assets/null.svg) | sync_by | uuid | NULL |

##### Foreign keys

- `instance` field of this table links to the `i_id` field of `Instances`.
- `repo` field of this table links to the `r_id` field of `Repositories`.

***

#### Tools

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | t_id | uuid | uuid_generatev4() |
|  | hostname | text |  |
|  | ip | inet |  |
|  | type | text |  |

#### InstanceTools

List external tools that an instance can relay on (monitoring, logger, ...).
Its content will not be updated by the interface.

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | i_id | uuid | uuid_generatev4() |
| ![Foreign key](./assets/link.svg) | tool | uuid |  |
| ![Foreign key](./assets/link.svg) | instance | uuid |  |
|  | created_at | timestampz | now() |
|  | created_by | uuid |  |
| ![nullable](./assets/null.svg) | sync_at | timestampz | NULL |
| ![nullable](./assets/null.svg) | sync_by | uuid | NULL |

##### Foreign keys

- `instance` field of this table links to the `i_id` field of `Instances`.
- `tool` field of this table links to the `t_id` field of `Tools`.

***

#### Parameters

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | p_id | uuid | uuid_generatev4() |
| ![Unique](./assets/fingerprint.svg) | key | text |  |
|  | description | text |  |
|  | type | text |  |
|  | deprecated | bool |  |
|  | created_at | timestampz | now() |
|  | created_by | uuid |  |

#### ConfiguratonValues

|  | Column | Type | Default |
|:--|:--------:|:------:|:---------:|
| ![Primary key](./assets/key.svg) | c_id | uuid | uuid_generatev4() |
| ![Foreign key](./assets/link.svg) | parameter | uuid |  |
| ![Foreign key](./assets/link.svg) | instance | uuid |  |
|  | i_value | int |  |
|  | t_value | text |  |
|  | a_value | text[] |  |
|  | created_at | timestampz | now() |
|  | created_by | uuid |  |
| ![nullable](./assets/null.svg) | sync_at | timestampz | NULL |
| ![nullable](./assets/null.svg) | sync_by | uuid | NULL |

##### Foreign keys

- `instance` field of this table links to the `i_id` field of `Instances`.
- `parameter` field of this table links to the `p_id` field of `Parameters`.
