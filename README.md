# DEPRECATED
**Notice: this module is now not maintained. Please see [coboxcoop/peerfs](https://github.com/coboxcoop/peerfs/) for the latest implementation**



## Usage

See [test.js](test.js) for examples.

#### TODO

- [ ] Move all of the functions over from hyperdrive to the top constructor instance. (e.g., readdir, stat)
- [ ] Improve performance and stability of index writes by using something othe
  than JSON.
- [ ] Allow resolveFork function to get access to the stat object of the file
  on that write so that it can make a more intelligent display or make better
decisions about the fork
- [ ] Allow forks to be unresolved cc @substack
- [ ] When writing, in the link we should record the seq of the hyperdrive, and on `whoHasFile`, checkout to that seq if its not the latest: https://github.com/karissa/peerfs/blob/master/index.js#L105-L106

## API

#### ```var fs = peerfs(storage, opts)```

Returns a [KappaCore](kappa-db/kappa-core) instance. Passes these options directly to that instance. 

In addition, peerfs accepts the following optional arguments:

* `resolveFork`: a function taking `values` of known versions of that file. If there are more than one here, there is a fork. By default, this returns the first item in the list. Overwrite this to get more fancy. 

#### ```fs.replicate()```

Replicate between two `peerfs` instances.

#### ```fs.readFile(filename, cb)```

Read asyncronously.

#### ```fs.writeFile(filename, content, cb)```

Write asyncronously.

#### ```fs.createWriteStream(filename, cb)```

Write to a stream.

#### ```fs.createReadStream(filename, cb)```

Read file from a stream.

## License

MIT


