# Ideas App

A place to store peoples idea in a style of reddit and twitter website

## User Stories

- Authenticate users
- Users can CRUD ideas
- Users can upvote/downvote ideas
- Users can bookmark ideas
- Users can comment ideas
- New Ideas can be seen in realtime

## Stack

- Database - PostgreSQL
- REST API - NestJS
- GraphQL API - NestJS
- Rest Frontend - Angular with ngrx
- GraphQL Frontend - React (native?) with Apollo Client


## Nest Work Step by Step

- At first I installed the project using Nestjs Cli and followed the documentation

```bash
    $ npm i -g @nestjs/cli
    $ nest new project-name
```
- Remove unnecessary files from the project

```bash
    rm webpack.config.js src/main.hmr.ts
```
- Made the .gitignore file (took the help from (gitignore.io)
- Then made the envioronment variable package.

```bash
    npm install dotenv
    or
    yarn add dotenv
```

- Then made a file called .env into the project. Initialize the port 4000
- Calling the dotenv package to the `main.ts` file

```ts
import 'dotenv/config';  // imported the package
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';
import { Logger } from '@nestjs/common';

const port = process.env.PORT || 8080;  // made the port

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(port); // pass the port to listen
  Logger.log(`Server running on http://localhost:${port}`, 'Bootstrap' ); // this line
}
bootstrap();

```
- Secondly, I created the Database connection using postgres. Also added package for ORM

```bash
    yarn add pg typeorm @nestjs/typeorm
```
- Install the pg admin