# jwt-auth

https://blog.ippon.fr/2017/10/12/preuve-dauthentification-avec-jwt/



# Start application

```
mvn spring-boot:run
```


# Test Application

## Retrieve Token

```
curl -s -X POST -H 'Accept: application/json;charset=UTF-8' -H 'Content-Type: application/json;charset=UTF-8' --data '{"username":"username","password":"password","rememberMe":false}' 'http://localhost:8080/api/auth' | jq
```

## Check security without Token 
```
curl -X GET 'http://localhost:8080/demo/secured' -H 'content-type: application/json' | jq 
```

## Check security with Token 
```
curl -X GET \
  'http://localhost:8080/demo/secured' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIxIiwidXNlcm5hbWUiOiJ1c2VyIiwiZW1haWwiOiJqd3RAaXBwb24uZnIiLCJyb2xlcyI6IkFETUlOIiwidXNlclNlY3JldCI6InNhbHRxdWlzZXJ0YXJpZW4iLCJleHAiOjE1NjY5MTQ0NTAsImlhdCI6MTU2NjkxNDE1MH0.w_GO-Ci_ghRz7mIVpbcEB6leBt6CuCiRO4yQcE9JV1td4V-pik3-rravI_u9il5Z251cMIyTzF7CT7o-Nh2K3A' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'accept-encoding: gzip, deflate' \
  -H 'cache-control: no-cache'
```

