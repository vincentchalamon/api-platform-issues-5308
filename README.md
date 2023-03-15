# Reproducer for https://github.com/api-platform/core/issues/5308

## Install

```shell
git clone git@github.com:vincentchalamon/api-platform-issues-5308
cd api-platform-issues-5308
composer install
```

## Start services

```shell
docker compose up --detach
symfony serve --daemon
```

## Create a resource entry

```shell
curl -X 'POST' \
  'http://127.0.0.1:8000/api/tests' \
  -H 'Accept: application/ld+json' \
  -H 'Content-Type: application/ld+json' \
  -d '{
  "name": "string"
}'
```

## List resource entries

```shell
curl -X 'GET' \
  'http://127.0.0.1:8000/api/tests' \
  -H 'Accept: application/ld+json'
```
