# mssql

## mssql
```bash
mkdir -p /opt/crudapi/mssql
chmod 777 /opt/crudapi/mssql

docker pull mcr.microsoft.com/mssql/server
docker tag mcr.microsoft.com/mssql/server mssql

docker rm -f mssql
docker run --name mssql \
    --restart=always \
    -e "ACCEPT_EULA=Y" \
    -e "SA_PASSWORD=Mssql1433" \
    -v "/opt/crudapi/mssql:/var/opt/mssql" \
    -p 1433:1433 \
    -d mssql
docker logs -f mssql
``` 

```bash
docker exec -it mssql /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P Mssql1433
```

## docs
[快速入门：使用 Docker 运行 SQL Server 容器映像](https://docs.microsoft.com/zh-cn/sql/linux/quickstart-install-connect-docker?view=sql-server-ver15&preserve-view=true&pivots=cs1-bash)

