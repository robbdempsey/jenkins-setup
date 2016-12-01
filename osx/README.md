### building the OSX image

```
docker build . -t {name}:{tag}
```

```
docker build . -t osx-jenkinx:1.0.0
```

### starting the image

```
docker run -p 49001:8080 -d \
	-v /var/run/docker.sock:/var/run/docker.sock \
	-v $PWD/jenkins:/var/jenkins_home osx-jenkins:1.0.0
```

this will mount the docker.sock for the docker instance running on your laptop into the container, as well as, the jenkins files into the current directory where you are running the container from.