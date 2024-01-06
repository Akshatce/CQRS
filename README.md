# CQRS POC Setup

## Pre-requisites
    JAVA 17
    MAven 
    MySQL DB
    Apache Kafka

## MySQL database setup : https://hevodata.com/learn/docker-mysql/

## Apache Kafka Setup on local : https://medium.com/@Ankitthakur/apache-kafka-installation-on-mac-using-homebrew-a367cdefd273 

## Run the services : mvn spring-boot:run


# cqrs-design-pattern

### CreateProduct Event

```
curl --location 'http://localhost:9191/products' \
--header 'Content-Type: application/json' \
--data '{
    "type": "CreateProduct",
    "product": {
        "name": "Books",
        "description": "KK publication",
        "price": 999
    }
}'
```
### UpdateProduct Event

```
curl --location --request PUT 'http://localhost:9191/products/1' \
--header 'Content-Type: application/json' \
--data '{
    "type": "UpdateProduct",
    "product": {
        "id": 1,
        "name": "Watch",
        "description": "Samsung latest model",
        "price": 58000.0
    }
}'
```
