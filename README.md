## Library of Useful Web Components


### Router

##### Description

Routing component designed to show content based on some kind of string route

##### Proposal

- Two main elements: `app-router` and `app-route`
- All `app-router` and `app-route` elements MUST be defined in the same shadow root. `app-router` will not attempt to traverse shadows.
- `app-route` elements MUST have a single child that is a `<template>` tag. If it does not, an error will be thrown.
- When an `app-router` is `connected`, it attaches a `MutationObserver` to itself and listens to any `app-router` elements that have been added to its current shadow root.
- When an `app-router` element has been found, it adds the `<app-route>` and its `<template>` child to a map to be associated via the `path`
- `app-router` will listen to any changes in routing (URL, Memory, hash, etc). When a change is detected, it will remove any DOM content that does not match the current path, while also inserting any content that does match the new path.



##### Sample Usage

```
<app-router>
  <app-route path="/home">
    <template>
      <div>Contents for Home</div>
    </template>
  </app-route>
  <app-route path="/product/:id">
    <template>
      <div>Contents for product detail page</div>
      <app-route path="/product/:id/comments">
         <template>
            Subroute for a product
         </template>
      </app-route>
    </template>
  </app-route>
</app-router>
```
