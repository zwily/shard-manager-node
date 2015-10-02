# shard-manager

Used for managing a set of shards in a consistent hashing ring. Extracted
from https://github.com/myspace/faye-redis-sharded-node.

## Usage

```javascript
var ShardManager = require('shard-manager');

var shardList = [
  {
    shardName: 'localhost:3000',
    shard: 'shard1' // This could also be an object, holding a redis conn or something
  },
  {
    shardName: 'localhost:3001',
    shard: 'shard2'
  }
];
var mgr = new ShardManager(shardList);

mgr.getShard('key1');
// shard2

mgr.getShard('key10');
// shard1
```
