# jenkins-setup

### running jenkins in docker 

``` 
$ docker pull jenkins
```

```
docker run -d -p 49001:8080 -v $PWD/jenkins:/var/jenkins_home -t jenkins
```

This will create a container with the jenkins files located in `$PWD/jenkins`. Once the container is up and running you can access jenkins at [http://127.0.0.1:49001](http://127.0.0.1:49001)


### Issues
Running jenkins locally is pretty simple.  However, there are a few differences between running it on your mac laptop versus a linux one. There are also issues when you want to run docker commands from jenkins pipelines.

There are plenty of articles out there discussing issues around docker in docker, as well as, specifics related to OSX file system issues. The [Dockerfile](./osx/Dockerfile) in the OSX directory is what I learned in trying to resolve some of those issues by accessing docker on the host laptop versus running in in the jenkins container itself.
