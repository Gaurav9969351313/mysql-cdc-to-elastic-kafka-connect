https://medium.com/@siddontang/how-to-sync-your-mysql-data-to-elasticsearch-ddae009243c1

https://towardsdatascience.com/stream-your-data-changes-in-mysql-into-elasticsearch-using-debizium-kafka-and-confluent-jdbc-b93821d4997b


Get All Indexes
http://localhost:9200/_aliases?pretty=true

Get All Records
http://localhost:9200/mysql-test-poc.inventory.city/_search?pretty=true&q=*:*

Kafka Connect UI
http://localhost:8003/

Mysql Adminer
http://localhost:8080

{
  "name": "JdbcSinkConnector",
  "connector.class": "io.confluent.connect.jdbc.JdbcSinkConnector",
  "topics": "TopicName_JdbcSinkConnector",
  "tasks.max": 1,
  "topic.prefix":"jdbc",
  "connection.url": "jdbc:mysql://localhost:5432/inventory",
  "connection.user": "root",
  "connection.password": "admin",
  "table.whitelist": "city",
  "mode":"timestamp+incrementing"
        
}

https://www.confluent.io/blog/kafka-elasticsearch-connector-tutorial/