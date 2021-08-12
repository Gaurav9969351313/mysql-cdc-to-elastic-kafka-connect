https://www.confluent.io/blog/kafka-elasticsearch-connector-tutorial/
https://javamana.com/2021/04/20210403045929239t.html

https://medium.com/@siddontang/how-to-sync-your-mysql-data-to-elasticsearch-ddae009243c1
https://towardsdatascience.com/stream-your-data-changes-in-mysql-into-elasticsearch-using-debizium-kafka-and-confluent-jdbc-b93821d4997b


### Update
PUT {{baseurl}}/connectors/simple-elasticsearch-connector/config HTTP/1.1
Content-Type: application/json

{
    "connector.class": "io.confluent.connect.elasticsearch.ElasticsearchSinkConnector",
 "connection.url": "http://elasticsearch:9200",
 "tasks.max": "1",
 "topics": "pg-football_players",
 "name": "simple-elasticsearch-connector",
 "type.name": "_doc",
 "value.converter": "org.apache.kafka.connect.json.JsonConverter",
 "key.converter": "org.apache.kafka.connect.storage.StringConverter",
 "value.converter.schemas.enable": "false",
 "schema.ignore": "true",
 "key.ignore": "true"
}