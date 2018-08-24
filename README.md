<p align="center"><img width=60% src="https://turtle-db.github.io/images/logo_full.png"></p>

<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#features">Features</a> •
  <a href="#contributors">Contributors</a> •
  <a href="#license">License</a> •
</p>

# Overview

turtleDB is a JavaScript framework for developers to build offline-first, collaborative web applications. It provides a developer-friendly API to access an in-browser database on top of IndexedDB.

It comes with built in document versioning and automatic server synchronization when paired with our back-end package [tortoiseDB](https://github.com/turtle-DB/tortoiseDB), as well as developer-controlled, flexible conflict resolution strategies for any document conflicts while collaborating.

You can check out our [API docs](https://turtle-db.github.io/api) and read more about the story behind project itself [here](https://turtle-db.github.io/about).

Note: for the best user experience we strongly recommend using Chrome.

<p align="center"><img width=80% src="/api-example.gif" /></p>

## Getting Started

### Install

```javascript
npm i turtledb
```

### Usage

```javascript
import TurtleDB from 'turtledb';
// or
const TurtleDB = require('turtledb');
```

```javascript
// Create a new database
const mydb = new TurtleDB('example');

// Link a remote tottoiseDB database to sync to
mydb.setRemote('http://127.0.0.1:3000');

// CRUD Operations - all promise based
mydb.create({ _id: 'firstTurtle', species: 'Sea Turtle' });
mydb.read('firstTurtle').then((doc) => console.log(doc));
mydb.update('firstTurtle', { species: 'Giant Turtle' });
mydb.mergeUpdate('firstTurtle', { name: 'Michelangelo' });
mydb.delete('firstTurtle');

// Sync
mydb.sync();
```

## Features

- Simple Promise-based API
- Integration with IndexedDB
- Document versioning and developer-controlled conflict resolution
- Synchronization with tortoiseDB and a MongoDB back-end
- Batching during synchronization
- Local database compaction

## Contributors

- **Andrew Houston-Floyd** - [Website](link)
- **Max Appleton** - [Website](https://maxiappleton.github.io/)
- **Steven Shen** - [Website](https://rockdinosaur.github.io/)

## License

This project is licensed under the MIT License.