# MongoStreamWritable

A writable stream that inserts or updates MongoDB documents.

# Usage

## Insert

    var MongoStream = require('mongo-stream-writable');

    var stream = new MongoStream({
    	url: 'mongodb://localhost/yourdb',
    	collection: 'yourcollection'
    });

    stream.write({ name: 'testdoc' });
    stream.end();

## Update

    var MongoStream = require('mongo-stream-writable');

    var stream = new MongoStream({
    	url: 'mongodb://localhost/yourdb',
    	collection: 'yourcollection',
    	upsert: true,
    	upsertFields: ['name'] //Optional, defaults to _id
    });

    stream.write({ name: 'testdoc', value: 42 });
    stream.end();