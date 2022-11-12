---
title: 'IndexDB, Client/Browser side Database'
date: 2022-09-25T22:30:08+05:30
tags: ['indexDB', 'store', 'Database']
series: ['blogs']
showDate: true
draft: true
---

## IndexDB

Author: self

- Some of my works [Github](https://github.com/rex-suresh)
- Contact through [Email](psureshk9@gmail.com)

### Introduction

> IndexDB is a data store of client/user. This DB comes handy when developing web apps which doesn't need continuos internet connection, or offline apps.

Things I have learnt.

- Creating a database.
- Creating a Object store.
- Understanding :
  - Request.
  - Transaction.
  - Object store.
  - Data base.
- Starting a transaction
  - Adding data into store.
  - Retrieving data from store.

### Brief explanation

#### Creating a database

For storing data, we need a database. And for opening a database we request the browser to open one for us.

```js
// Syntax is as follows.
const indexDBRequest = window.indexedDB.open('DBName', 1); // 1 is version number

// Creates Database of version 1 by default
const request = window.indexedDB.open('newDB');

// A version number can be provided to .open along with name to request for that version database.
const request = window.indexedDB.open('newDB2', 2);
```

- Here we are requesting the window.indexDB to open a database for us by providing the database name.

#### Creating a object store

In a database we need tables or maps to store data as a collection, This indexDB stores them as Object stores.

```js
// 'database' is the instance of a indexDB, returned as a result from `window.indexedDB.open` request.
// can be also taken by :
const database = event.target.result; // when using in a onupgradeneeded event or onsuccess event.

// Creating a object store, one has to provide the name of store and
// the key of the object store so that it can be indexed accordingly
const objectStore = database.createObjectStore('fruits', { keyPath: 'name' });
```

### Reason for this blog / discovery

> Something to explain what made you know this.
