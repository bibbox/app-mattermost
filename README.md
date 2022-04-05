# Mattermost BIBBOX application

## Standalone installation
Clone the github repository, chmod the data foler and run docker-compose up. If necessary change the ports and volume mounts in `docker-compose.yml`.

`sudo git clone https://github.com/bibbox/app-mattermost`

`sudo chmod 777 -R data/`

`docker-compose up`

## Install within BIBBOX

Within BIBBOX you can use the [BIBBOX](https://bibbox.readthedocs.io/en/latest/) to install a lot of software tools. After the installation is finished you can start your application in the dashboard. 

Create an account and off you go 

## Docker Images Used
* [postgres:13-alpine](https://hub.docker.com/layers/postgres/library/postgres/13-alpine/images/sha256-0d3137d83b50573cc17d5998a62f79075d4088daec4d408a240e960a99f5da4e?context=explore)
* [mattermost/mattermost-team-edition:6.3](https://hub.docker.com/layers/mattermost-team-edition/mattermost/mattermost-team-edition/6.3/images/sha256-604f5f146213e2220fb5caa9c4e44553e68904d1bada7fd4d6ff471f96bb2af4?context=explore)

## Mounted Volumes

- ./data/mattermost/config:/mattermost/config:rw
- ./data/mattermost/data:/mattermost/data:rw
- ./data/mattermost/logs:/mattermost/logs:rw
- ./data/mattermost/plugins:/mattermost/plugins:rw
- ./data/app/mattermost/client/plugins:/mattermost/client/plugins:rw
- ./data/mattermost/bleve-indexes:/mattermost/bleve-indexes:rw
