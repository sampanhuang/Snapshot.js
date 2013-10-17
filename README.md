Snapshot.js
===========

Node.js app for slicing and dicing paginated chunks of data with easy sorting and filtering.

Dependencies
-----------

All dependencies can be installed with `bower install` and `npm install`, however the list is as follows:

 * <a href="http://underscorejs.org/">Underscore.js</a> (client and server);
 * <a href="http://socket.io/">Socket.IO</a> (client and server);
 * <a href="http://nodejs.org/">Node.js</a> (server);
 * <a href="http://square.github.io/crossfilter/">Crossfilter</a> (server);
 * <a href="http://pivotal.github.io/jasmine/">Jasmine</a> (grunt);

Quick Start
-----------

Once a WebSocket connection has been successfully established, you're able to bootstrap Snapshot, passing in the WebSocket (Socket.IO) reference as a dependency.

```javascript
snapshot.bootstrap(socket);
```

You then need to tell Snapshot what collection it's going to be creating snapshots of.

```javascript
snapshot.setCollection(json);
```

Snapshot listens for three events natively, and these are handled automatically.

 * `snapshot/perPage` &ndash; Set amount per page;
 * `snapshot/pageNumber` &ndash; Set current page number;
 * `snapshot/sortBy` &ndash; Set order column and ascending/descending;

When the collection has been updated, Snapshot emits the `snapshot/contentUpdated` event, passing through the snapshot as the first argument.

Angular
-----------

Snapshot also comes with a bundled Angular module for easier interaction. Simply add `$snapshot` as a dependency and you have everything you need.