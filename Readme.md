# Dokku with postgres

```
dokku postgres:create sonar_postgres
dokku postgres:link sonar_postgres sonar
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

