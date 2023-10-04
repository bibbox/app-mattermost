# mattermost BIBBOX application

This container can be installed as [BIBBOX APP](https://bibbox.readthedocs.io/en/latest/ "BIBBOX App Store") or standalone. 

After the docker installation follow these [instructions](INSTALL-APP.md).

## Standalone Installation 

Clone the github repository. If necessary change the ports in the environment file `.env` and the volume mounts in `docker-compose.yml`.

```
git clone https://github.com/bibbox/app-mattermost
cd app-mattermost
chmod 777 -R data/
docker network create bibbox-default-network
docker-compose up -d
```

The main App can be opened and set up at:
```
http://localhost:8065
```

## Install within BIBBOX

Visit the BIBBOX page and find the App by its name in the store. Click on the symbol and select install. Then fill the parameters below and name your App, click install again.

## Docker Images used
  - [postgres](https://hub.docker.com/r/postgres) 
  - [mattermost/mattermost-team-edition](https://hub.docker.com/r/mattermost/mattermost-team-edition) 


 
## Install Environment Variables
  - POSTGRES_USER_ENV = User for Postges DB
  - POSTGRES_USER_PW = Password for Postgres DB

  
The default values for the standalone installation are:
  - POSTGRES_USER_ENV = user
  - POSTGRES_USER_PW = changethispasswordinproductionenvironments

  
## Mounted Volumes
### postgres Container
  - *./data/db/postgresql/data:/var/lib/postgresql/data*
### mattermost/mattermost-team-edition Container
  - *./data/mattermost/config:/mattermost/config:rw*
  - *./data/mattermost/data:/mattermost/data:rw*
  - *./data/mattermost/logs:/mattermost/logs:rw*
  - *./data/mattermost/plugins:/mattermost/plugins:rw*
  - *./data/app/mattermost/client/plugins:/mattermost/client/plugins:rw*
  - *./data/mattermost/bleve-indexes:/mattermost/bleve-indexes:rw*

