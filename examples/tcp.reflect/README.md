# tcp.reflect
Listens on tcp port `12345` and will echo back whatever is sent to the server, broadcasting to all clients.

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
Connect each client first, then send `Hello, one` from first client, then send `Hello, two` from second client.
```bash
$ nc localhost 12345
Hello, one
Hello, one
Hello, two
```
```bash
$ nc localhost 12345
Hello, one
Hello, two
Hello, two
```
