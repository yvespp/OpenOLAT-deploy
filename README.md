# README

Packages [OpenOLAT](https://github.com/OpenOLAT/OpenOLAT) as a Docker image.

Repo based on files from [this pull request](https://github.com/OpenOLAT/OpenOLAT/pull/101/). 


## Build & run

The following command will build and run:
* Postgresql image with the db init script added
* Tomcat with the openolat app

```bash
docker compose up --build
```

Try it out:
* url: http://localhost:8088
* initial username: administrator
* initial password: openolat

### Build images only

```bash
docker build --pull openolat -t open-olat
docker build --pull postgres -t postgres
```
