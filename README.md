
###### Outputs
```
➜  bin http POST localhost:8080/profile username=unamerkel password=changeme \
    firstName=Una lastName=Merkel email=unamerkel@example.com
HTTP/1.1 200
Connection: keep-alive
Content-Type: application/json
Date: Sun, 24 May 2020 13:19:18 GMT
Keep-Alive: timeout=60
Transfer-Encoding: chunked

{
    "email": "unamerkel@example.com",
    "firstName": "Una",
    "id": 2,
    "imageFileContentType": null,
    "imageFileName": null,
    "lastName": "Merkel",
    "password": "changeme",
    "username": "unamerkel"
}
```

```
➜  bin http localhost:8080/profile/unamerkel
HTTP/1.1 200
Connection: keep-alive
Content-Type: application/json
Date: Sun, 24 May 2020 13:19:27 GMT
Keep-Alive: timeout=60
Transfer-Encoding: chunked

{
    "email": "unamerkel@example.com",
    "firstName": "Una",
    "id": 2,
    "imageFileContentType": null,
    "imageFileName": null,
    "lastName": "Merkel",
    "password": "changeme",
    "username": "unamerkel"
}
```

```
➜  bin http localhost:8080/profile/russcolombo
HTTP/1.1 404
Connection: keep-alive
Content-Length: 0
Date: Sun, 24 May 2020 13:19:34 GMT
Keep-Alive: timeout=60

```

```
➜  Downloads http -f POST http://localhost:8080/profile/unamerkel/image file@pic.jpg
HTTP/1.1 200
Connection: keep-alive
Content-Length: 35
Content-Type: text/plain;charset=UTF-8
Date: Sun, 24 May 2020 13:20:45 GMT
Keep-Alive: timeout=60

You successfully uploaded 'pic.jpg'
```

```
➜  Downloads http localhost:8080/profile/unamerkel/image
HTTP/1.1 200
Connection: keep-alive
Content-Length: 153542
Content-Type: image/jpeg
Date: Sun, 24 May 2020 13:20:49 GMT
Keep-Alive: timeout=60
```