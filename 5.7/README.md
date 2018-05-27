# About this repository

This repository is docker setting of mysql 5.7 which includes mecab parser.

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

