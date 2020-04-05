# Learning Docker

### Important Command

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

* List your images
```
$ docker image ls
```

* List of Containers
```
$ docker container ls
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
#### Power shell command 
* To see list of files
```
ls  
```

### References 
* [Docker Images and Containers for ASP.NET Core](https://app.pluralsight.com/library/courses/docker-images-containers-aspdotnet-core/table-of-contents)
* https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/docker/building-net-docker-images?view=aspnetcore-3.1
