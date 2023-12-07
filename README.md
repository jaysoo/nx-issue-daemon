Demo of daemon bug due tsconfig.json content.

Run
```
nx build demo
```

See this error in daemon logs:

```
[NX Daemon Server] - 2023-12-07T18:33:34.391Z - Handled REQUEST_PROJECT_GRAPH. Handling time: 45. Response time: 2.
/private/tmp/ts-simple/node_modules/nx/src/hasher/native-task-hasher-impl.js:19
            delete tsconfig.compilerOptions.paths;
                            ^

TypeError: Cannot convert undefined or null to object
    at new NativeTaskHasherImpl (/private/tmp/ts-simple/node_modules/nx/src/hasher/native-task-hasher-impl.js:19:29)
    at new InProcessTaskHasher (/private/tmp/ts-simple/node_modules/nx/src/hasher/task-hasher.js:47:15)
    at handleHashTasks (/private/tmp/ts-simple/node_modules/nx/src/daemon/server/handle-hash-tasks.js:18:24)
    at process.processTicksAndRejections (node:internal/process/task_queues:95:5)
    at async handleResult (/private/tmp/ts-simple/node_modules/nx/src/daemon/server/server.js:110:16)
    at async handleMessage (/private/tmp/ts-simple/node_modules/nx/src/daemon/server/server.js:84:9)
    at async /private/tmp/ts-simple/node_modules/nx/src/daemon/server/server.js:45:9
```
