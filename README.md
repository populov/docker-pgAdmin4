**pgAdmin4 in docker container - Version 3.0**
-

[![](https://images.microbadger.com/badges/image/chorss/docker-pgadmin4.svg)](https://microbadger.com/images/chorss/docker-pgadmin4) [![](https://images.microbadger.com/badges/version/chorss/docker-pgadmin4.svg)](https://microbadger.com/images/chorss/docker-pgadmin4)[![](https://images.microbadger.com/badges/license/chorss/docker-pgadmin4.svg)](https://microbadger.com/images/chorss/docker-pgadmin4)

|          NAME          | Data Type  | REQUIRED                       |
|------------------------|------------|--------------------------------|
| SERVER_PORT            | Integer    | NO                             |
| SERVER_MODE            | Boolean    | YES                            |
| PGADMIN_SETUP_EMAIL    | String     | NO*                            |
| PGADMIN_SETUP_PASSWORD | String     | NO*                            |
| MAIL_SERVER            | String     | NO*                            |
| MAIL_PORT              | Integer    | NO*                            |
| MAIL_USE_SSL           | Boolean    | NO*                            |
| MAIL_USE_TLS           | Boolean    | NO*                            |
| MAIL_USERNAME          | String     | NO*                            |
| MAIL_PASSWORD          | String     | NO*                            |
| MAIL_DEBUG             | Boolean    | NO                             |
| UID                    | Integer    | NO                             |
| GID                    | Integer    | NO                             |

`*` -> if SERVER_MODE set false

Example commands
-

**Quick start**

`$ docker run -d -p 5050:5050 chorss/docker-pgadmin4`

`$ docker run -d -p 5050:5050 -v /home/user/data:/data chorss/docker-pgadmin4`


**Backup and Restore in pgAdmin4 (pg_dump, pg_restore)**

To use restore and backup you need to set the path

`File -> Preferences -> Binary` the paths set to `/usr/bin`

**Data Storage Outside of the Container**

 This will store session, configuration and storage on the given volume.
 The application user within the container will change it's uid/gid to the
 given values and will use this uid/gid to write to the volume-directory.

 
`docker run -d -p 5050:5050 -e UID=2301 -e GID=2301 -v /home/user/data:/data chorss/docker-pgadmin4`
