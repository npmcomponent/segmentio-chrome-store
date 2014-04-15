*This repository is a mirror of the [component](http://component.io) module [segmentio/chrome-store](http://github.com/segmentio/chrome-store). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/segmentio-chrome-store`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*

# chrome-store

  tiny wrapper around chrome.storage

## Installation

  Install with [component(1)](http://component.io):

    $ component install segmentio/chrome-store

## Example

```js
var store = require('chrome-store')('sync');

// single

store.set('a', 1, function(err){
  if (err) throw err;
  store.get('a', function(err, value){
    if (err) throw err;
    assert(1 == value);
  });
});

// multi

store
  .set('a', 1)
  .set('b', 2)
  .set('c', 3)
  .end(function(err){});

store
  .get('a')
  .get('b')
  .get('c')
  .end(function(err, obj){
    assert(1 == obj.a);
    assert(2 == obj.b);
    assert(3 == obj.c);
  });
```


## License

  MIT
