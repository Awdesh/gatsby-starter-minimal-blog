---
date: "2017-02-01"
title: Quick note on Google Guice. 
category: java, programming, beginners 
---

Recently I had a chance to use Google Guice in a Java Service for managing dependencies. We were managing dependencies manually between business objects in the application code, Guice took care of the manual labor of dependencies between objects.

Few major components that are needed for Guice to implement in applicatoin.

1.) Module -: Every interface and its implementation gets bound inside a module. A module binds a implementation to the interface. Every module can be configured with some of the bindings which is taken by Binder class.

Lets binder be a instance of Binder class.

```
    binder.bind(interface.class).to(implementation.class);
```

2.) Injector -: Now injector creates an injector based on module. Then instance of the injector can be used to call methods from the API.

```
    Injector injector = Guice.createInjector(new Module());
    Interface instance =  injector.getInstance(Implementation.class);
```           