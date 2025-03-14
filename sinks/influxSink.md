## `influxdb` sink

The `influxdb` sink uses the official [InfluxDB golang client](https://pkg.go.dev/github.com/influxdata/influxdb-client-go/v2) to write the metrics to an InfluxDB database in a **blocking** fashion. It provides only support for V2 write endpoints (InfluxDB 1.8.0 or later).


### Configuration structure

```json
{
  "<name>": {
    "type": "influxdb",
    "database" : "mymetrics",
    "host": "dbhost.example.com",
    "port": "4222",
    "user": "exampleuser",
    "password" : "examplepw",
    "organization": "myorg",
    "ssl": true,
    "flush_delay" : "1s",
    "batch_size" : 100,
    "meta_as_tags" : [],
  }
}
```

- `type`: makes the sink an `influxdb` sink
- `database`: All metrics are written to this bucket 
- `host`: Hostname of the InfluxDB database server
- `port`: Portnumber (as string) of the InfluxDB database server
- `user`: Username for basic authentification
- `password`: Password for basic authentification
- `organization`: Organization in the InfluxDB
- `ssl`: Use SSL connection
- `flush_delay`: Group metrics coming in to a single batch
- `batch_size`: Maximal batch size
- `meta_as_tags`: move meta information keys to tags (optional)

