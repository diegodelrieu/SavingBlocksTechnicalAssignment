## SavingBlocks Technical assignment

### 📕 Instructions

This is a boilerplate template to get you started on the SavingBlocks technical assignment. Feel free to make all necessary changes to the boilerplate, including updating the dependencies.

**You are free not to use this boilerplate and build this from scratch using a stack of your choice. If you do, please still follow the delivery instructions**

You can read below a number of informations on how to get started with this template.

### Requirements


Start by copying this template in a private github repository.

![image](https://user-images.githubusercontent.com/46749544/160638681-dc3d4209-d3be-4a32-a4df-16766d2a38f8.png)



For this assignment the candidate is expected to complete the following features :

- As a user, I should be able to a find visual interface that allows me to connect to a blockchain (of your choice) through a crypto web wallet (you can use metamask or walletconect for instance)

And one of the following: 

- As a user, I should find a form in which I am able to create a transaction on that blockchain to send funds to an address of my choice and add a note for this transaction (stored in the db along with the transaction hash from the blockchain)
- As a user, I can visualize via a line chart the evolution of this wallet's balance.

**Feel free to reuse any existing component to gain time 🏎️**



**_Extra_**
If you have time feel free to add any of the following features

- Unit testing
- Display all the transactions in the UI: use the existing table

#### 📦 Delivery

Please to facilitate the readability of your code don't build on feature on the `master` branch and create a new one instead.
When you are done open a Pull Request with a short description from your branch to master.

Then add `diegodelrieu` as a collaborator to your github repository and add his as a reviewer for your pull request !

#### Stack

- React.js
- TypeScript
- Node.js
- Nest.js
- Postgres
- Docker


### Quick start

Clone this template in your local machine

Then install dependencies.

```bash
# install server dependencies

cd ./server && npm i

# instal client dependencies

cd ../client && npm i
```

Now Let's check our Demo, for that run the following command

```bash
cd ../ && sudo docker-compose --file docker-compose-dev.yml up
```

it will be served on `http://localhost:3000`

## Client

Client has been created with create-react-app and located in `./project-name/client`

#### Development

In develpoment mode the client will be run in a container built with `./client/Dockerfile.dev` and will be exposed on port 3000, with docker volumes every change thats been saved will be reflected within the running container.

## Database

Enviornment variables will be located in the docker-compose file.`
and will contain our database credentials :

```
POSTGRES_USER=admin
POSTGRES_PASSWORD=admin
POSTGRES_DB=pern_db
```

## Enjoy 🎉
