### Router

##### Description

Routing component designed to show content based on some kind of string route


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
