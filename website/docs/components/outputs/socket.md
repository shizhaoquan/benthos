---
title: socket
type: output
status: stable
categories: ["Network"]
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/output/socket.go
-->

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';


Sends messages as a continuous stream of line delimited data over a
(tcp/udp/unix) socket by connecting to a server.

```yaml
# Config fields, showing default values
output:
  socket:
    network: unix
    address: /tmp/benthos.sock
```

Each message written is followed by a delimiter (defaults to '\n' if left empty)
and when sending multipart messages (message batches) the last message ends with
double delimiters. E.g. the messages "foo", "bar" and "baz" would be written as:

```
foo\n
bar\n
baz\n
```

Whereas a multipart message [ "foo", "bar", "baz" ] would be written as:

```
foo\n
bar\n
baz\n\n
```

## Fields

### `network`

The network type to connect as.


Type: `string`  
Default: `"unix"`  
Options: `unix`, `tcp`, `udp`.

### `address`

The address (or path) to connect to.


Type: `string`  
Default: `"/tmp/benthos.sock"`  

```yaml
# Examples

address: /tmp/benthos.sock

address: localhost:9000
```


