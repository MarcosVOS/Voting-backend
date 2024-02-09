# voting-api

### 🇺🇸 Project developed during RocketSeat's NLW Event 

#### The project consists of an API in which the user creates a poll and monitors voting in real time.

#### Technologies used: 
- NodeJS
- TypeScript 
- Prisma
- Fastify
- Zod
- ioredis
- database: PostgreSQL

---   
### Endpoints: 
#### **[ POST ]** -  http://localhost:3333/polls
This endpoint, for the user to create a vote

It is structured as follows.

the title of the poll

and options the poll options

Content-Type: application/json
```
  {
    "title":"poll title",
    "options":["option One","option Two","option Three"]
  }
```

#### **[ GET ]** - http://localhost:3333/polls/:pollId
To perform the search you need the poll id which is returned in the creation endpoint and send by params in ```pollId```

#### **[ POST ]** - http://localhost:3333/polls/:pollId/votes
This endpoint is for the user to cast their vote in a poll.
Receives data both through body and params. 
The body is ```pollOptionId``` the id of the option that the user will cast their vote and by params the value ```pollId``` which is the id of the poll

Content-Type: application/json
``` 
  {
    "pollOptionId": "b0fe54a6-b8bf-441c-989e-c1960e0aa3fa"
  }
```

---
### How to run:
```
// To install project dependencies
npm i

// To raise the necessary services for the application to work, including a PostgreSQL container and a Redis container
docker compose up -d  

// To run in development mode
npm run dev

// If you want to see the database
npx prisma studio 
```

**If you want to execute and need to fill in the environment variables, there is an example file default.env**
