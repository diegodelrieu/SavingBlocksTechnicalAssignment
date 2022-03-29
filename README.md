## 5% Technical assignment

### 📕 Instructions

This is a boilerplate template to get your started faster on the 5% technical assignment.

You can read below a number of informations on how to get started with this template.

### Requirements

Start by copying this template in a private github repository.

This template should provide you a good foundation to complete your task.

For this assignment the candidate is expected to complete the following feature :

```
- As a user, I should be able to a find visual interface that allows me to connect to a blockchain (of your choice) through a crypto web wallet (you can use metamask or walletconect for instance)

- As a user, I should find a form in which I am able to create a transaction on that blockchain to move funds to an address of my choice and add a note for this transaction (stored in the db allowing with the transaction hash), ⚠️ **update the existing form**.
```

**_Extra_**
If you have time feel free to add any of the following features

- Unit testing
- Display all the transactions in the UI: use the existing table

#### 📦 Delivery

Please to facilitate the readability of your code don't build on feature on the `master` branch and create a new one instead.
When you are done open a Pull Request with a short description from your branch to master.

#### Stack

- React.js
- Redux
- Node.js
- Nest.js
- Postgres
- Docker

### Prerequisites

Make sure you have the below installed on your machine.

- [x] **Docker** : https://docs.docker.com/engine/install/
- [x] **Docker-Compose** : https://docs.docker.com/compose/install/
- [x] **Node** : https://nodejs.org/en/

### Quick start

Clone this repo to your local machine

```
git clone https://github.com/nadavpodjarski/postgres-express-react-typescript-boilerplate.git project-name
```

Before we run our container lets calm down our editor and npm install dependecies locally.
For that let's run the following command

```bash
# install server dependencies

cd project-name/server && npm i

# instal client dependencies

cd ../client && npm i
```

Now Let's check our Demo, for that run the following command

```bash
cd ../ && sudo docker-compose --file docker-compose-dev.yml up
```

it will be served on `http://localhost:3000`

**Replace project-name with your own**

## Client

Client has been created with create-react-app and located in `./project-name/client`

#### Development

In develpoment mode the client will be run in a container built with `./client/Dockerfile.dev` and will be exposed on port 3000, with docker volumes every change thats been saved will be reflected within the running container.

#### Production

In production mode the client build will be created and will run in a container built with `./client/Dockerfile`.
The client build/static-files will be served with nginx server and will be exposed on port 80.

#### Environment Variables

Enviornment variables are located in `./client/.env` but can be declared into the dockerfile itself under ENV or in the docker compose file under enviornemt property.
**In order to use docker stack deploy** its needed to use one of the other options and not env_file.

**note that nginx server has a minimalistic configuration**

## Data-base

Postgres data-base is created with an official postgres image which can be found in docker hub https://hub.docker.com/_/postgres

Enviornment variables will be located in the docker-compose file.`
and will contain our database credentials :

```
POSTGRES_USER=admin
POSTGRES_PASSWORD=admin
POSTGRES_DB=pern_db
```

Volumes of our database will be located in `./server/database/data`

> Production volume is located in `./server/data/prod` </br>
> Development volume is located in `./server/data/dev`

#### Data-base connection

Data-base connection is handled with ormconfig.json that is located at `./server/ormconfig.json`
and will contain postgres credentials to establish connection to our data-base.
Thanks to https://github.com/vishnubob/wait-for-it for the wait-for-it.sh script, we can set that the server image will run only after getting confirmation that postgres container is available.
by that we wont get connection failures due to bad order of docker composing.

## Docker compose

### Development

To establish a development environment, simply run the following command from the project root folder.

```bash
sudo docker-compose --file docker-compose-dev.yml up
```

On save changes in client and server, containers will be automatically updated, no need to restart any servers.
</br>

## Good to know

- To drop the use of sudo run the folowing command in your terminal

```bash
sudo usermod -aG docker $USER
```

- If you are making changes within the dockerfiles you will need to rebuild them, for that add the --build flag to the docker compose up command.

## Enjoy 🎉
