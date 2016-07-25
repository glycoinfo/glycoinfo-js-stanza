# glycoinfo-stanza

## Install the Docker tools in advance

please install [docker tools](https://docs.docker.com/) in advance.


## Download glycoinfo-stanza

```
$ git clone https://github.com/glycoinfo/glycoinfo-stanza.git
```


## See the stanza working


run docker-compose and stanza

```
$ git clone https://github.com/glycoinfo/glycoinfo-stanza.git
$ cd glycoinfo-stanza/
$ docker-compose up
```
Open http://localhost:8082/stanza/ with your web browser.



## Scaffold a new stanza

generate new stanza 

```
$ cd stanza_provider/
$ docker ps
CONTAINER ID        IMAGE                              COMMAND                  CREATED             STATUS              PORTS                    NAMES
36be404ce18e        glycoinfostanza_glycoinfo-stanza   "/stanza/ts_0.0.8_lin"   50 minutes ago      Up 50 minutes       0.0.0.0:8082->8080/tcp   glycoinfostanza_glycoinfo-stanza_1

$ docker exec glycoinfostanza_glycoinfo-stanza_1 /stanza/ts_0.0.8_linux_amd64/ts new {stanza_name} 
```


## deploy to glycoinfo web server

glycoinfo-stanza is deploied automatically by Jenkins when you push the update by git. 

```
$ git add {youre updated file}
$ git commit -m "your comment"
$ git push
``` 

Open http://fly.glycoinfo.org:8082/stanza/ with your web browser.
