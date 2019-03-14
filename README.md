Alpine MariaDb image.

You can configure options using environment variables ("." are replaced by "_d_" and "-" are replaced by "_s_"). Example:
```
MARIADB_s_10_d_3__INNODB_DOUBLE_WRITE=0
MYSQLD__INNODB_LOG_FILE_SIZE="128M"
MYSQLD__INNODB_BUFFER_POOL_SIZE="1024M"
MYSQLD__INNODB_BUFFER_POOL_INSTANCES=2
MYSQL__PASSWORD="xxxxx"
```


##TODO
- Compile static add -DBUILD_SHARED_LIBRARIES=OFF to cmake or 
    -DDISABLE_SHARED=YES -DWITH_PIC=1