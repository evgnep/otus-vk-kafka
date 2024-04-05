Создать топик, 2 партиции, 3 репл фактор
```shell
docker exec -ti kafka-otuskafka /usr/bin/kafka-topics --create --topic topic1 --partitions 2 --replication-factor 3 --config min.insync.replicas=2 --bootstrap-server kafka1:9191
```

Отправить сообщение
```shell
docker exec -ti kafka-otuskafka /usr/bin/kafka-console-producer --topic topic1 --bootstrap-server kafka1:9191
```

Получить описание топика
```shell
docker exec -ti kafka-otuskafka /usr/bin/kafka-topics --describe --topic topic1 --bootstrap-server kafka1:9191
```

Получить сообщения
```shell
docker exec -ti kafka-otuskafka /usr/bin/kafka-console-consumer --from-beginning --topic topic1 --bootstrap-server kafka1:9191 
```

