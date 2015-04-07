# docker-wildfly
This image is based on latest Ubuntu image.
It automatically installs oracle java 8 package and downloads Wildfly 8.2.
There is integrated jdbc drivers for
*PostgreSQL
*MySQL
*MS SQL Server/Sybase from jtds
*Oracle 12.0.1.0 drivers

Here is a note for Oracle drivers:
A lot of tool-jars are put to tmp folder after run (for ex. ojdbc_g.jar wich provides additional verbosity in logs, and i18n jars there too)

At this moment XA ds for Oracle is not tested, but all other configs are validated.

It's better to start this image linked to database containers from start
Here is my command to run this:
```shell
docker run --name=wildfly -P -d --link oraxe11:oradb stormsw/wildfly
```
