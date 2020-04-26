# elasticsearch-docker

### Container build

```
docker-compose build
```

### Container start up

```
docker-compose up -d
```

### Check 

```
curl -X GET http://localhost:9200/
```

### Put and search text

```
curl -X PUT http://localhost:9200/mytest/test/1 -H 'content-type: application/json' -d '
{
  "title" : "memo",
  "text"  : "hogehoge"
}'
```

```
curl -X GET http://localhost:9200/mytest/test/_search -H 'content-type: application/json' -d '
{
  "query": {"match": {"title":"memo"}}
}'
```

### Stop

```
docker-compose down
```

### Remove

```
docker-compose down --rmi all
```
