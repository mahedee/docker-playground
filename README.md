# Learning Docker

## Important commands
### Dot net commands

* To build dot net application  
```
dotnet build
```

* To run dot net application  
```
dotnet run
```
* To see dot net version
```
dotnet --version
```
### Docker commands

* Docker version 
```
$ docker version
```

* List your images
```
$ docker image ls
```

* List of Containers
```
$ docker container ls
or
$ docker ps
```

* To stop docker container
```
$ docker stop <container id>
```

* Run a command in a running container
```
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```
Example
```
$ docker exec -ti 34717 sh -c "echo a && echo b"
or
$ docker exec -ti my_container sh -c "echo a && echo b"
or 
$ docker exec -ti my_container sh -c "dir"
```
* To run docker composer
```
$ docker-compose up
```

* Running the CLI in windows container
```
$ docker run --rm -it mcr.microsoft.com/dotnet/core/runtime:3.1
```
* The following command will run an ASP.NET Core console app in a container that you can access in your web browser at http://localhost:8000.
```
docker run --rm -it -p 8000:80 mcr.microsoft.com/dotnet/core/samples:aspnetapp
````
#### Power shell command 
* To see list of files
```
ls  
```

### References 
* https://docs.docker.com/engine/reference/commandline/docker/
* [Docker Images and Containers for ASP.NET Core](https://app.pluralsight.com/library/courses/docker-images-containers-aspdotnet-core/table-of-contents)
* https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/docker/building-net-docker-images?view=aspnetcore-3.1
* https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md
