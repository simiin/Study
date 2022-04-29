# MySQL

## Comment 조회

- table comment
    ```sql
    SELECT 
        table_name, table_comment
    FROM
        information_schema.tables
    WHERE
        table_schema = 'DB 이름' AND table_name = '테이블 이름';
    ```

- column comment
    ```sql
    SELECT
        table_name, column_name, column_comment
    FROM
        information_schema.columns
    WHERE
        table_schema = 'DB 이름' AND table_name = '테이블 이름';
    ```

## DB backup

```sh
mysqldump -u [user id] -p [password] [original database name] > [backup database name to create].sql

# example
mysqldump -u test_user -p test_db > backup_test_db.sql
passowrd : 123456
```

## Table backup

```sh
mysqldump -u [user id] -p [password] [database name] [origin backup table name] > [table name to backup].sql

# example
mysqldump -u test_user -p test_db test_table > backup_test_table.sql
passowrd : 123456
```

## DB restoration

```sh
mysql -u [user id] -p [password] [database name to restore] < [backup database].sql

# example
mysql -u test_user -p test_db < backup_test_db.sql
passowrd : 123456
```

## Table restoration

```sh
mysql -u [user id] -p [password] [database name to restore] < [backup table].sql

# example
mysql -u test_user -p 123456 test_db < backup_test_table.sql
passowrd : 123456
```

---

# Reference

- https://extbrain.tistory.com/97
    - comment 조회
- https://server-talk.tistory.com/30
    - data backup