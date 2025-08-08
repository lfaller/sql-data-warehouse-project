# Start the sql server in docker on a mac

```bash
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=YourStrong@Password123" \
   -p 1433:1433 --name sqlserver --hostname sqlserver \
   -v sqlserver-data:/var/opt/mssql \
   -d mcr.microsoft.com/mssql/server:2022-latest
```

# Other useful commands

```bash
# Start the server
docker start sqlserver

# Stop the container
docker stop sqlserver

# Check if it's running
docker ps

# Check all containers (running and stopped)
docker ps -a

# View the logs
docker logs sqlserver
```

# Connect to the SQL server on the command line

```bash
# Connect to the running container and open sqlcmd
docker exec -it sqlserver /opt/mssql-tools18/bin/sqlcmd -S localhost -U sa -P "YourStrong@Password123" -C
```