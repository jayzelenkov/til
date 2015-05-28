---
title: Node.js cluster disconnect
tags: [JavaScript]
description: Understand what does cluster.disconnect do.
---

The documentation of the nodejs for [cluster API][cluster] gives the following example code to terminate a worker process:

```js
worker.on('listening', function(address) {
    worker.disconnect();
    timeout = setTimeout(function() {
        worker.kill();
    }, 2000);
});
```

In my case the worker always waits for 2 seconds before being terminated. This made me wonder why `disconnect` is even needed?

`worker.disconnect()` is used for graceful termination. `disconnect` instructs worker process to close all servers and waits for the __close__ event.

`disconnect` can fail at disconnecting the worker process. This can happen when a worker receives another request while executing the disconnect procedure. That's why there is `worker.kill()`.

`worker.kill()` sends __SIGTERM__ by default and kills the worker process.

__SIGTERM__ may fail at operating system level so that worker process will still be running. To ensure the worker process will be killed, send a __SIGKILL__ signal:

```js
worker.kill("SIGKILL");
```


[cluster]: https://nodejs.org/api/cluster.html
