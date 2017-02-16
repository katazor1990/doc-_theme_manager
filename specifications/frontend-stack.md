
[Specifications](../../specifications.md)
===

Frontend
---

### React/Baobab/Djax-client workflow

It is a event driven MVC workflow.
React componments manage rendering over the DOM, each componment have its own internal state.
Baobab store data as an immutable tree with cursors and events.
It is possible to plug React componment state on baobab cursors to automate rendering over data updates.
Djax-client allow to define services, which connect to API to interact with.

![Frontend rendering loop](./assets/graph/frontend-render-loop.svg)

In this diagram, React componment relay DOM events to Controller, calling or not services from Djax-client, updating data in baobab tree. React componment get notified through baobab event that it should render.
