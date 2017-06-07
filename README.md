# MongoWritableStream

A writable stream that inserts or updates MongoDB documents.

# Usage

## Insert

    var MongoWritableStream = require('mongo-writable-stream');

    var stream = new MongoWritableStream({
        url: 'mongodb://localhost/yourdb',
        collection: 'yourcollection'
    });

    stream.write({ name: 'testdoc' });
    stream.end();

## Update

    var MongoWritableStream = require('mongo-writable-stream');

    var stream = new MongoWritableStream({
        url: 'mongodb://localhost/yourdb',
        collection: 'yourcollection',
        upsert: true,
        upsertFields: ['name'] //Optional, defaults to _id
    });

    stream.write({ name: 'testdoc', value: 42 });
    stream.end();

# History

Added support for JSON parsable strings. It can now be used as a stream for [bunyan](https://github.com/trentm/node-bunyan)