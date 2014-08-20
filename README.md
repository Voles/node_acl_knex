Node Acl KnexBackend
=============

A Knex.js backend for node_acl

Knex is a query builder for PostgreSQL, MySQL and SQLite3 in Node, The Knex backend is to be used as an adapter for [OptimalBits/node_acl](https://github.com/OptimalBits/node_acl).

[![BuildStatus](https://travis-ci.org/christophertrudel/node_acl_knex.svg?branch=0.1.6)](https://travis-ci.org/christophertrudel/node_acl_knex)[![Coverage Status](https://img.shields.io/coveralls/christophertrudel/node_acl_knex.svg)](https://coveralls.io/r/christophertrudel/node_acl_knex)[![Dependency Status](https://david-dm.org/christophertrudel/node_acl_knex.svg)](https://david-dm.org/christophertrudel/node_acl_knex)[![devDependency Status](https://david-dm.org/christophertrudel/node_acl_knex/dev-status.svg)](https://david-dm.org/christophertrudel/node_acl_knex#info=devDependencies)

##Features & Documentation
**Please note that this library currently supports Postgres. MySql and SQLite support coming soon.**

Please see [OptimalBits/node_acl](https://github.com/OptimalBits/node_acl).


##Installation

Using npm:

```javascript
npm install acl
npm install knex

npm install pg (for use with Postgres)
npm install mysql (for use with MySql, coming soon)
npm install sqlite3 (for use with SQLite, coming soon)

npm install acl-knex
```

Setup tables:
```
node setup.js <<db_name>> <<username>> <<password>> <<prefix>>

eg: node setup.js 'travis_ci_test', 'postgres', '12345', 'acl'
```



#Quick Start
```javascript
	Acl = require('acl');
	AclKnexBackend = require('acl_knex');
	knex = require('knex');

	var db = knex({
		client: 'postgres',
		connection: {
			host: '127.0.0.1',
			port: 5432,
			user: 'postgres',
			database: 'travis_ci_test'
		}
	});
	
	var acl = new Acl(new AclKnexBackend(db, 'acl_'));
```

#Testing
```javascript
npm test
```

Follow me on Twitter [thetrudel](http://twitter.com/thetrudel)
