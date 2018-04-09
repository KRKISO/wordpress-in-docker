# wordpress-in-docker

***Installation***

MYSQL Container setup auf Docker VM. Bitte "mypassword" durch ein sicheres Passwort ändern!
```
docker run --detach --name=test-mysql --env="MYSQL_ROOT_PASSWORD=mypassword" mysql
```

Die Verlinkung und Installation kann mit dem folgenden befehl ausgeführt werden. Falls man parameter geändert hat, muss man diese bei dem folgenden Befehl auch anpassen.
```
docker run --detach --name test-wordpress --link test-mysql:mysql -P wordpress
```

Die Container können durch den folgenden Befehl angezeigt werden.
```
docker ps
```
Ports und Name des Container werden aufgelistet.
```
14c9b3c8cbbe        wordpress           "docker-entrypoint.s…"   33 minutes ago      Up 33 minutes       0.0.0.0:32768->80/tcp    test-wordpress
789a65e428f4        mysql               "docker-entrypoint.s…"   About an hour ago   Up 42 minutes       0.0.0.0:6603->3306/tcp   test-mysql
```
Danach kann man durch den Port in meinem Fall http://192.168.60.101:32768 und die IP der Docker VM auf das Wordpress WI zugreifen.
