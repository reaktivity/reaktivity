# tcp.echo
Listens on tcp port `12345` and will echo back whatever is sent to the server.

### Requirements
 - JDK 11 or higher.

### Install modular Java runtime
```bash
$ ./rymw install
...
linked modules
generated launcher
```

### Start reaktivity engine
```bash
$ ./ry start
started
```

### Verify behavior
```bash
$ nc localhost 12345
Hello, world
Hello, world
```
