Setup Contrfinder Docker

## Build docker

1. docker-compose up -d --build
2. import db by run command line: 

```cat contrfinder_staging_20210419.dump | docker exec -i contrfinder_db pg_restore -U postgres -d contrfinder_dev```

3. update .env file
4. docker-compose exec app composer install

## PHP Unit test
run command line:

```docker-compose exec app ./vendor/bin/phpunit --colors=always tests/Feature/Http/Controllers/InventoryItemControllerBulkChangeStaffTest```