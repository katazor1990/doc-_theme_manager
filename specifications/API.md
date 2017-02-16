
### API design

This section will help define routes from the API using `VERB: /route` syntax. By convention, `:var` in route definition represent variable placeholder.
 
#### Session

Manage authentication.

##### GET: /session

Get the current user uuid. can also respond `401 please login` if not authenticated.

##### POST: /session/login

Send credentials and start user session, return `200` and user uuid if success, `401 wrong credentials` otherway.

##### POST: /session/logout

Destroy user session. Alway return `200` even if there were no session.

#### Users & roles

Manage users and roles.

##### GET: /user/role

List all availlable roles.

##### GET: /user?role=:role&limit=100&offset=0

List all users, can be filtered over user role and paginated.

##### POST: /user

Create new user

##### GET: /user/:user

Get specific user.

##### PUT: /user/:user

Edit specific user.

##### DELETE: /user/:user

Delete specific user

##### PUT: /user/:user/role

Change specific user role.

***

#### Nodes

Manage nodes (servers).

##### GET: /node?type=:type&limit=100&offset=0

List all nodes, can be filtered and paginated.

`:type` define if list contain physical or virtual nodes.

##### POST: /node

Create node.

##### GET: /node/:node

Get specific node.

##### PUT: /node/:node

Edit specific node.

##### DELETE: /node/:node

Delete specific node.

#### Tools

##### GET: /tool?type=:type&limit=100&offset=0

Get tools list, can be filtered and paginated.

##### POST: /tool

Create tool.

##### GET: /tool/:tool

Get specific tool.

##### PUT: /tool/:tool

Edit specific tool.

##### DELETE: /tool/:tool

Delete specific tool.

***

#### Parameters

##### GET: /parameter?type=:type&limit=100&offset=0

Get parameter list, can be filtered and paginated.

##### POST: /parameter

Create parameter.

##### GET: /parameter/:parameter

Get specific parameter.

##### DELETE: /parameter/:parameter

Delete specific parameter.

##### PUT: /parameter/:parameter/deprecated

Edit parameter to set it deprecated.

#### Repositories

##### GET: /repository

Get respositories list.

##### GET: /repository/:repository

Get specific respositories.

***

#### Instances

##### GET: /instance?type=:type&limit=100&offset=0

Get instances list.

##### POST: /instance

Create instance.

##### GET: /instance/:instance

Get specific instance.

##### PUT: /instance/:instance

Edit specific instance.

##### DELETE: /instance/:instance

Delete speficic instance.

##### GET: /instance/:instance/node

Get node list by specific instance.

##### POST: /instance/:instance/node

Associate node to instance.

##### DELETE: /instance/:instance/node/:node

Delete specific node's instance.

##### GET: /instance/:instance/configuration

Get specific instance's configuration.

##### POST: /instance/:instance/configuration

Create instance's configuration.

##### PUT: /instance/:instance/configuration/:parameter

Edit specific configuration's parameter.

##### DELETE: /instance/:instance/configuration/:parameter

Delete specific configuration's parameter.

##### GET: /instance/:instance/tool

Get instance's tools list.

##### POST: /instance/:instance/tool

Add specific instance's tool.

##### DELETE: /instance/:instance/tool/:tool

Delete specific instance's tool.

##### GET: /instance/:instance/version

Get instance's version list.

##### POST: /instance/:instance/version/:repository

Add specific respositorie's version by instance.

##### PUT: /instance/:instance/version/:repository

Edit specific respositorie's version by instance.

##### DELETE: /instance/:instance/version/:repository

Delete specific respositorie's version by instance.

***

#### Deployment

##### POST: /deployment/:instance

Deploy instance .

##### POST: /deployment/:instance/node

Deploy instance's node deployment.

##### POST: /deployment/:instance/node/:node

Deploy specific node to instance deployment.

##### POST: /deployment/:instance/configuration

Deploy specific instance 's configuration.

##### POST: /deployment/:instance/configuration/:parameter

Deploy specific instance's parameter.

##### POST: /deployment/:instance/tool

Deploy specific instance's tools.

##### POST: /deployment/:instance/tool/:tool

Deploy specific instance's tool.

##### POST: /deployment/:instance/version

Dploy specific version.

##### POST: /deployment/:instance/version/:repository

Deploy specific respositoriy's version.
