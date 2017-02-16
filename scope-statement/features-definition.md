
[Scope statement](../../scope-statement.md)
===

Features definition
---

### Users and roles

All users should not be able to access all the features. There will be roles with different level of accessibility on every data. Roles ability to use will be declared in the feature description.

We do not see any necesity of managing roles dynamicaly. There will be four ones for now :
- Suspended
  - nothing
- Guest
  - view instances
  - Edit his own profile
- Developer
  - Guest capabilities
  - Edit/deploy configuration on instance
  - Edit/deploy version on instance
- DevOps
  - Developer capabilities
  - Edit/deploy infrastructure on instance
- Admin
  - DevOps capabilities
  - Manage users and roles

#### Actions

- create
- edit
- promote
- revoke
- delete

#### Model

- firstname
- lastname
- email
- phone
- password
- role
- creation date
- creator

### Instances

Instances are about the whole ecosystem of matlo dedicated to some usage, it can be the main SaaS instance or even some other dedicated to a specific client.

#### Actions

- create
- edit
- delete
- deploy
- restore

#### Model

- name
- description
- creation date
- creator

### Instance infrastructure

Infrastuctures define the physicals and virtuals nodes plus the services to install on them. It also contains the side tools to connect.

#### Actions

- add physical
- bootstrap physical (chef)
- delete physical
- add node
- edit node services
- edit node configuration (resources, network)
- delete node
- add tool
- delete tool
- deploy (send to chef)
- restore (get from chef)

#### model

- physicals
  - hostname
  - ip
  - CPU
  - Memory
- nodes
  - hostname
  - host
  - ip
  - mac
  - CPU
  - Memory
  - services
- tools
  - type
  - hostname
  - ip

### Instance configuration

Configuration manage the instance specific details.

To allow developers to add new configuration key without modifying this tool, there must be a way to add new configuration keys.

#### Actions

- add key
- deprecate key
- edit
- deploy
- restore

#### Model

- domains & aliases
  - application
  - shared
  - REST API
  - website
  - Stripe webhook
  - backoffice
- mailer
  - domain
  - key
  - addresses
- captcha
  - api
  - key
- stripe
  - secret
  - public
- limits
- secret
- postgres
  - user
  - database
  - password
- custom

### Instance version

Versions define the code to deploy on instance.

#### Actions

- edit
- deploy
- restore

#### Model

- backend
- frontend
- backoffice
- website
