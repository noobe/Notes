# import vs require

# Are NodeJS Modules singleton?

Node.js modules can behave like Singletons, but they are not guaranteed to be always singleton. There are two reasons for this and both are mentioned in the official Node.js documentation:

Node’s module caching mechanism is case-sensitive:
For example, require(‘./foo’) and require(‘./FOO’) return two different objects, irrespective of whether or not ./foo and ./FOO are the same file

Modules are cached based on their resolved filename:
Since modules may resolve to a different filename based on the location of the calling module (loading from node_modules folders), it is not a guarantee that require(‘foo’) will always return the exact same object, if it would resolve to different files.