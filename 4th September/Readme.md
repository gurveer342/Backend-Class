<!-- Microsoft Windows [Version 10.0.22631.4112]
(c) Microsoft Corporation. All rights reserved.

C:\Users\hp>mongosh
Current Mongosh Log ID: 66d822cdf58795e9262710bb
Connecting to:          mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.3.0
Using MongoDB:          7.0.14
Using Mongosh:          2.3.0

For mongosh info see: https://www.mongodb.com/docs/mongodb-shell/

------
   The server generated these startup warnings when booting
   2024-09-04T09:53:41.619+05:30: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted
------

test> Guri
ReferenceError: Guri is not defined
test> use Guri
switched to db Guri
Guri> db.createCollection
[Function: createCollection] AsyncFunction {
  apiVersions: [ 1, Infinity ],
  returnsPromise: true,
  serverVersions: [ '0.0.0', '999.999.999' ],
  topologies: [ 'ReplSet', 'Sharded', 'LoadBalanced', 'Standalone' ],
  returnType: { type: 'unknown', attributes: {} },
  deprecated: false,
  platforms: [ 'Compass', 'Browser', 'CLI' ],
  isDirectShellCommand: false,
  acceptsRawInput: false,
  shellCommandCompleter: undefined,
  help: [Function (anonymous)] Help
}
Guri> db.userinsertMany
Guri.userinsertMany
Guri> db.create("Student")
TypeError: db.create is not a function
Guri> db.createCollection("Student")
{ ok: 1 }
Guri> db.userinsertMany([{name:"Guri",age:19,marks:50,subject:Mathematics},{name:"Jalpari",age:21,marks:100,subject:Home Science},{name:"Saini",age:22,marks:34,subject:Commerce}])
Uncaught:
SyntaxError: Unexpected token, expected "," (1:115)

> 1 | db.userinsertMany([{name:"Guri",age:19,marks:50,subject:Mathematics},{name:"Jalpari",age:21,marks:100,subject:Home Science},{name:"Saini",age:22,marks:34,subject:Commerce}])
    |
                                                         ^
  2 |

Guri> db.userinsertMany([{name:"Guri",age:19,marks:50,subject:"Mathematics"},{name:"Jalpari",age:21,marks:100,subject:"Home Science"},{name:"Saini",age:22,marks:34,subject:"Commerce"}])
TypeError: db.userinsertMany is not a function
Guri> db.user.insertMany([{name:"Guri",age:19,marks:50,subject:"Mathematics"},{name:"Jalpari",age:21,marks:100,subject:"Home Science"},{name:"Saini",age:22,marks:34,subject:"Commerce"}])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('66d8261ef58795e9262710bc'),
    '1': ObjectId('66d8261ef58795e9262710bd'),
    '2': ObjectId('66d8261ef58795e9262710be')
  }
}
Guri> db.user.find().pretty();
[
  {
    _id: ObjectId('66d8261ef58795e9262710bc'),
    name: 'Guri',
    age: 19,
    marks: 50,
    subject: 'Mathematics'
  },
  {
    _id: ObjectId('66d8261ef58795e9262710bd'),
    name: 'Jalpari',
    age: 21,
    marks: 100,
    subject: 'Home Science'
  },
  {
    _id: ObjectId('66d8261ef58795e9262710be'),
    name: 'Saini',
    age: 22,
    marks: 34,
    subject: 'Commerce'
  }
]
Guri> db.user.findOner();
TypeError: db.user.findOner is not a function
Guri> db.user.findOne();
{
  _id: ObjectId('66d8261ef58795e9262710bc'),
  name: 'Guri',
  age: 19,
  marks: 50,
  subject: 'Mathematics'
}
Guri> db.user.find({grade:"A+"})

Guri> db.student.bulkWrite([{updateOne:filter:{name:"Jaiko"},update:{$set:{grade:"A"}}}},{updateOne:{filter:{name:"Boby" }, update: { $set: { grade: "B" } } } }, { updateOne: { filter: { name: "Naiv" }, update: { $set: { grade: "A+" } } } }, { updateOne: { filter: { name: "CHinky" }, update: { $set: { grade: "A" } } } }] );
Uncaught:
SyntaxError: Unexpected token, expected "," (1:39)

> 1 | db.student.bulkWrite([{updateOne:filter:{name:"Jaiko"},update:{$set:{grade:"A"}}}},{updateOne:{filter:{name:"Boby" }, update: { $set: { grade: "B" } } } }, { updateOne: { filter: { name: "Naiv" }, update: { $set: { grade: "A+" } } } }, { updateOne: { filter: { name: "CHinky" }, update: { $set: { grade: "A" } } } }] );
    |                                        ^
  2 |

Guri> db.Student.bulkWrite([ { updateOne: { filter: { name: "JaiGuri> db.Student.bulkWrite([ { updateOne: { filter: { name: "JaiGuri> db.Student.bulkWrite([ { updateOne: { filter: { name: "Jaiko" }, update: { $set: { grade: "A" } } } }, { updateOne: { filter: { name: "Boby" }, update: { $set: { grade: "B" } } } }, { updateOne: { filter: { name: "Naiv" }, update: { $set: { grade: "A+" } } } }, { updateOne: { filter: { name: "CHinky" }, update: {
 $set: { grade: "A" } } } }] );
{
  acknowledged: true,
  insertedCount: 0,
  insertedIds: {},
  matchedCount: 0,
  modifiedCount: 0,
  deletedCount: 0,
  upsertedCount: 0,
  upsertedIds: {}
}
Guri> db.Student.find({age:22,marks: 90})

Guri> db.Student.find({age:22,marks:90})

Guri> db.Student.find({grade:"A+"})

Guri> db.Student.find({grade:"A"})

Guri> db.estimatedDocumentCount()
TypeError: db.estimatedDocumentCount is not a function
Guri> db.student.estimatedDocumentCount()
0
Guri> db.student.estimatedDocumentCount()
0
Guri> db.user.insertOne({date:ISODate()});
{
  acknowledged: true,
  insertedId: ObjectId('66d82aaef58795e9262710bf')
}
Guri> db.Student.bulkWrite([
... ...     { updateOne: { filter: { name: "Jaiko" }, update: { $set: { grade: "A" } } } },
... ...     { updateOne: { filter: { name: "Boby" }, update: { $$set: { grade: "B" } } } },
... ...     { updateOne: { filter: { name: "Naiv" }, update: { $$set: { grade: "A+" } } } },
... ...     { updateOne: { filter: { name: "Chinky" }, update: {
 $set: { grade: "A" } } } }
... ... ]);
Uncaught:
SyntaxError: Unexpected token, expected "," (6:0)

  4 | ...     { updateOne: { filter: { name: "Naiv" }, update: { $set: { grade: "A+" } } } },
  5 | ...     { updateOne: { filter: { name: "Chinky" }, update: { $set: { grade: "A" } } } }
> 6 | ... ]);
    | ^
  7 |

Guri> db.Student.bulkWrite([ { updateOne: { filter: { name: "JaiGuri> db.Student.bulkWrite([ { updateOne: { filter: { name: "JaiGuri> db.Student.bulkWrite([ { updateOne: { filter: { name: "Jaiko" }, update: { $set: { grade: "A" } } } }, { updateOne: { filter: { name: "Boby" }, update: { $set: { grade: "B" } } } }, { updateOne: { filter: { name: "Naiv" }, update: { $set: { grade: "A+" } } } }, { updateOne: { filter: { name: "CHinky" }, update: {
 $set: { grade: "A" } } } }] );
{
  acknowledged: true,
  insertedCount: 0,
  insertedIds: {},
  matchedCount: 0,
  modifiedCount: 0,
  deletedCount: 0,
  upsertedCount: 0,
  upsertedIds: {}
}
Guri> db.Student.find({ grade: "A+" } -->