
[Scope statement](../../scope-statement.md)
===

### Technical constraints

#### Languages

In order to keep consistency over company developments, this project will follow the main product technical stack and guidelines. It will then be separated in two parts : backend and frontend.

##### backend

The backend will use the famous [Nodejs](https://nodejs.org/en/docs/) REST API framework [express](http://expressjs.com/).

It will be wroten is ES2015 and converted to regular JavaScript by [babel](https://babeljs.io/)

Most of the following express modules may be usefull :

- [body-parser](https://www.npmjs.com/package/body-parser)
- [cookie-parser](https://www.npmjs.com/package/cookie-parser)
- [dolman](https://www.npmjs.com/package/dolman)
- [express-session](https://www.npmjs.com/package/express-session)
- [passport-local](https://www.npmjs.com/package/passport-local)

##### Frontend

The frontend will use the [Baobab](https://github.com/Yomguithereal/baobab)/ [React](https://facebook.github.io/react/)/ [djax-client](https://www.npmjs.com/package/djax-client) stack for single-page-webapp including :
- [baobab-react](https://github.com/Yomguithereal/baobab-react)
- [baobab-router](https://github.com/jacomyal/baobab-router)

The interface integration will be done through [SASS](http://sass-lang.com/) with [bootstap](http://getbootstrap.com/).

ES2015 convertion, SASS compilation and assets bundle will be manage with [webpack](https://webpack.github.io/docs/)

As this tool will be for internal use only, there is no necesity to support other browsers than [Google Chrome](https://www.google.fr/chrome/browser/desktop/index.html?brand=CHBD&gclid=CLD6toXp_dECFUkQ0wodaUUMlA) in his most recent release.

#### DataBase Managment System

As in the languages sections, the DBMS will follow the main product stack then use PostgreSQL (9.5).

#### Deployment

This project will include his own chef cookbook to handle the deployment.

***

#### External APIs

##### OVH

[OVH](https://www.ovh.com/fr/) is the current domain names provider, this project will then have to connect to their REST API to manage domain names redirections.

> [node-ovh](https://github.com/ovh/node-ovh)

##### online.net

[online.net](https://www.online.net/fr) is the physical servers provider, in order to guarentee server and ip availlability, this tool will have to connect to their REST API.

> No official library/client found at this time.

##### Chef

As all data are transmitted to nodes through the chef server, it seems pretty obvious that this project will have to connect to it.

> [chef-api](https://github.com/normanjoyner/chef-api)


##### Gitlab

It would be nice to have ability to fetch available revisions directly from gitlab to prevent typo.

> [gitlab](https://github.com/node-gitlab/node-gitlab)
> [node-gitlab](https://github.com/repo-utils/gitlab)
