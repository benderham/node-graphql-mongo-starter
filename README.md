# Node, GraphQL and MongoDB Starter Project
A starter project for a Node, GraphQL and MongoDB powered API.

## Installation
### Fork this repository
[GitHub: Fork a repo](https://help.github.com/en/github/getting-started-with-github/fork-a-repo)

### Check for any depencency updates
```bash
  $ npx npm-check-updates
```

### Review updates
Review updates and apply them to `package.json`. Major updates may introduce breaking changes, you may need to make fixes if you apply them.
```bash
  $ npx npm-check-updates -u
```

**Note:** If you come across a breaking change in a major dependency update and
happen to fix it, please submit a PR with your fix. On the other hand if for
some reason you couldn't fix it, please raise a Bug Report Issue.

### Install dependencies
```bash
  $ npm install
```

### Setup MongoDB via MongoDB Atlas
1. [Create an Atlas Account](https://docs.atlas.mongodb.com/tutorial/create-atlas-account/#create-an-service-account)
2. [Deploy a Free Tier Cluster](https://docs.atlas.mongodb.com/tutorial/deploy-free-tier-cluster/)
3. [Whitelist Your Connection IP Address](https://docs.atlas.mongodb.com/tutorial/whitelist-connection-ip-address/)
4. [Create a MongoDB User for Your Cluster](https://docs.atlas.mongodb.com/tutorial/create-mongodb-user-for-cluster/)

Once your Cluster and MongoDB User are created, you can get your **Connection String** from the Connect Menu, and add it to your `.env` file. See [Connect Your Application](https://docs.atlas.mongodb.com/driver-connection/#connect-your-application) for more
information.

### Sample .env
```
  API_PORT=4000
  DATABASE=<mongodb-connection-string>
  FRONTEND_URL=<front-end-url>
```

## Usage
### Running in Development
```bash
  $ npm start
```

### GraphQL Playground
`http://localhost:4000/playground`

### GraphQL Endpoint
`http://localhost:4000/graphql`

### Sample Schema and Resolvers
This project has a sample `User` GraphQL Schema, Data Model and Resolvers.
Follow these instructions above to seed the database with sample users to get started.

#### Populate Database Contents
```bash
  $ npm run loadsampledata
```

#### Delete Database Contents
```bash
  $ npm run deletesampledata
```

#### Sample User Mutation
```graphql
  mutation createUser($username:String!, $email: String!) {
    createUser(username: $username, email: $email) {
      _id
      username
      email
    }
  }

  {
    "username": "testuser",
    "email": "testuser@gmail.com"
  }
```

#### Sample User Query
```graphql
  query users {
    users {
      _id
      username
      email
    }
  }
```

## Built with
* [GraphQL Yoga 🧘](https://github.com/prisma-labs/graphql-yoga)
* [MongooseJS](https://mongoosejs.com/)
* [No-Sweat™ Eslint and Prettier Setup](https://github.com/wesbos/eslint-config-wesbos)

## Roadmap
* User Authentication (JWT)
* User Permissions
* Tests (Jest)
* Deployment
* Client (Next.js)

## Acknowledgments
* [Wes Bos](https://github.com/wesbos)
* [Lydia Hallie](https://github.com/lydiahallie/react-graphql-starter)

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests and the README as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)