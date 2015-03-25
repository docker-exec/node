# Docker Exec Image: NodeJS

A Dockerfile describing an container capable of executing NodeJS source files.

# Build

```sh
git clone https://github.com/docker-exec/node.git
docker build -t dexec/node .
```

# Usage

In a directory containing a script e.g. foo.js, run:

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.js:/tmp/dexec/build/foo.js \
    dexec/node foo.js
```

## Passing arguments to the script

Arguments can be passed to the script using any of the following forms:

```
-a argument
--arg argument
--arg=argument
```

Each argument passed must be prefixed in this way, e.g.

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.js:/tmp/dexec/build/foo.js \
    dexec/node foo.js \
    --arg='hello world' \
    --arg=foo \
    --arg=bar
```
