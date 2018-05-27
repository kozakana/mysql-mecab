# About this directory

This directory is docker setting of mysql 8.0 which includes mecab parser.

## Settings
### my.cnf
/etc/mysql/conf.d/docker.cnf
```
[mysqld]
loose-mecab-rc-file=/etc/mecabrc
innodb_ft_min_token_size=1
```

### Add init SQL
overrite docker-entrypoint.sh

```
echo "INSTALL PLUGIN mecab SONAME 'libpluginmecab.so';" | "${mysql[@]}"
```

