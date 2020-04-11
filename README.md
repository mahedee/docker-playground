# Learning Docker

## Important commands
### Dot net commands

* To restore dot net dependencies
```
$ dotnet restore
```

* To build dot net application  
```
$ dotnet build
```

* To run dot net application  
```
$ dotnet run
```

* To publish the application
```powershell
$ dotnet publish
```

* To see dot net version
```
$ dotnet --version
```
* To install dotnet package
```
Syntax:
$ dotnet add package <PackageName> 
Example:
$ dotnet add package MailKit 
```
Tips: run command from project's directory
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
Get back to the host OS, type
$ exit
```

* The following command will run an ASP.NET Core console app in a container that you can access in your web browser at http://localhost:8000.
```
docker run --rm -it -p 8000:80 mcr.microsoft.com/dotnet/core/samples:aspnetapp
````

* Mounting a folder name 'api' into the container 
```powershell
$ docker run --rm -it -v ${PWD}:C:\api mcr.microsoft.com/dotnet/core/runtime:3.1
```
```text
here ${PWD} means current directory of host machine map to the directory C:\api into the container
```

* To run application inside a container 
```text
For windows
```
```powershell
$ C:\api\bin\Debug\netcoreapp2.0>dotnet api.dll
```
```text
For Linux
```
```powershell
$ root@01b2ded02d27:/api/bin/Debug/netcoreapp3.1/publish# dotnet api.dll
```

* To inspect network and other information of a container
```text
$ docker inspect <container id>
```

* Publishing a host port with container port 
```text
For Windows container
```
```powershell
$ docker run --rm -it -v ${PWD}:C:\api -p 6060:80 mcr.microsoft.com/dotnet/core/aspnet:3.1  
```
```text
Here 6060 is host machine port and 80 is container port
```
```text
For Linux container
```
```powershell
$ docker run --rm -it -v ${PWD}:/api -p 6060:80 mcr.microsoft.com/dotnet/core/aspnet:3.1      
```

* Build a docker file 
```
Syntax:
$ docker build -t <any tag name> directory
Example:
$ docker build -t aspnetcore/generator .   
Explanation: 
Here aspnetcore/generator is tag name and '.' means current directory
```

* Run a docker file 
```
Syntax:
$ docker run --rm -it -p <host port>:<image port> <any tag name>
Example:
$ docker run --rm -it -p 8777:80 test2  
Explanation: 
Here test2 is tag name of the image which already running
```

* To remove/stop all images 
```
Syntax:
$ docker image prune -a
```

* Login to docker and push an image
```
$ docker login 
$ docker push mahedee/simpleapi  
Explanation: 
Here mahedee/simpleapi is the tag name of the image
```

* Setting the API Port with an Environment Variable inside a containerr
```
$ export ASPNETCORE_URLS=http://+:80
```
* To see docker event in json format
```
$ docker events --format '{{json .}}'

Tips:
Run this command in another windows
```
* To run docker compose file
```
$ docker-compose up
```

* To detach docker compose file
```
$ docker-compose up -d
```

* To see the log while running docker compose file
```
$ docker-compose logs -f
```
* Stop and remove containers, networks, images, and volumes
```
$ docker-compose down
```

* Remove one or more images
```
$ docker image rm <repository>:<tag>
Example:
$ docker image rm mahedee/webapi:build
```
#### Power shell command 
* To see list of files
```powershell
$ ls  
```

* Write something in a file 
```powershell
$echo hello > hello.txt
```


### References 
* https://docs.docker.com/engine/reference/commandline/docker/
* [Docker Images and Containers for ASP.NET Core](https://app.pluralsight.com/library/courses/docker-images-containers-aspdotnet-core/table-of-contents)
* https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/docker/building-net-docker-images?view=aspnetcore-3.1
* https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md
* https://docs.microsoft.com/en-us/visualstudio/containers/container-build?view=vs-2019