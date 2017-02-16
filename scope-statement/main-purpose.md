
[Scope statement](../../scope-statement.md)
===

Context
---

### Main purpose

In order to manage multiple instance of matlo on several servers, matlo IT team developed some [Chef](https://docs.chef.io/) [cookbooks](https://docs.chef.io/cookbooks.html). Those cookbooks use the [data bag](https://docs.chef.io/data_bags.html) concept to store the configuration accross all instances.

The matlo data bag have to store the complete instance definition with the following information :
- physical servers details :
  - hostname
  - ips
- virtual servers  :
  - physical host
  - ip
  - mac address
  - CPU
  - memory
- nodes roles
  - data or calculation node
  - backend
  - reverse proxy
  - ...
- backend configuration :
  - API keys
    - mailer
    - map provider
    - captcha
    - billing provider
    - ...
  - database credentials
  - Elasticsearch parameters
  - application limits
- domain names for each instance front
- versions :
  - backend
  - frontend
  - back-office

***

Due to data structure complexity, some tools have been developed on CI to prevent failure when pushing modifications to production servers. Those tools only stop propagation from developer work station to production at push time.

In order to prevent developers from pushing mistakes to CI server, we consider developing this application. It should allow users to manage instances with the following actions :

- to create/modify/delete instance
- to create/modify/delete instance infrastructure
- to deploy version on instance
- to deploy configuration on instance
- to configure domains redirections on domain names provider
- to guarantee validity of infrastucture configuration (physical server, ips)
