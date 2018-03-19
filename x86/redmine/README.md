# redmine

## redmine项目管理系统

```
version: '3.1'

services:

  redmine:
    image: redmine
    restart: always
    ports:
      - 8080:3000
    environment:
      REDMINE_DB_MYSQL: db
      REDMINE_DB_PASSWORD: example
    volumes:
      - "./configuration.yml:/usr/src/redmine/config/configuration.yml"

  db:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: example
      MYSQL_DATABASE: redmine
    volumes:
      - "./mysqld.cnf:/etc/mysql/mysql.conf.d/mysqld.cnf"
      - "./mysql:/var/lib/mysql"
```

- configuration.yml为redmine主配置文件
- mysqld.cnf为mysql数据库配置文件
- 按当前docker-compose启动后，数据库信息将保存在当前目录的mysql文件夹下
