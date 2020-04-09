#FROM mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim AS base
#FROM mcr.microsoft.com/dotnet/core/runtime:3.1
FROM mcr.microsoft.com/dotnet/core/sdk:3.1
WORKDIR /WebAPI

# Copy all to the current directory
# Here first '.' means all and second '.' means current directory
# Here '/api' is the current directory
COPY . .

# Now we are in /api directory

# Restore dotnet application
RUN dotnet restore

# Publish dotnet application and set output directory as publish
RUN dotnet publish -o /publish 
#RUN dotnet publish
# COPY bin/Debug/netcoreapp3.1/publish .
# Configure the container to be run as executable

ENTRYPOINT [ "dotnet", "/publish/WebAPI.dll" ]

