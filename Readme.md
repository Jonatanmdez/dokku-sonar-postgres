# Sonar in Dokku  with postgres

```
dokku apps:create sonar
dokku postgres:create sonar_postgres
dokku postgres:link sonar_postgres sonar
```

If you use dokku-limit, you need to increase the limit 

```
dokku limit:set sonar web memory=2G
```

In your local

```
git clone 
git remote add dokku dokku@yourinstance
git push dokku
```


## Bind manual between variables

View variable of postgres
```
dokku postgres:info sonar_postgres
```

Manual bind
```
dokku config:set sonar SONARQUBE_JDBC_URL=jdbc:postgresql://dokku-postgres-sonar-postgres/sonar_postgres SONARQUBE_JDBC_USERNAME=postgres SONARQUBE_JDBC_PASSWORD={$put-password-of-bind}
```

