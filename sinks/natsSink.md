## `nats` sink

The `nats` sink publishes all metrics into a NATS network. The publishing key is the database name provided in the configuration file


### Configuration structure

```json
{
  "<name>": {
    "type": "nats",
    "database" : "mymetrics",
    "host": "dbhost.example.com",
    "port": "4222",
    "user": "exampleuser",
    "password" : "examplepw",
    "meta_as_tags" : [],
  }
}
```

- `type`: makes the sink an `nats` sink
- `database`: All metrics are published with this subject
- `host`: Hostname of the NATS server
- `port`: Portnumber (as string) of the NATS server
- `user`: Username for basic authentification
- `password`: Password for basic authentification
- `meta_as_tags`: print all meta information as tags in the output (optional)
