# Prisma ORM Fundamental

**1 Mar, 25 -- 11 August, 25**

- [Github Link](https://github.com/Apollo-Level2-Web-Dev/PrismaMastery)

## 55-1 Introduction and Overview of Prisma

- library / framework (frontend) -- ORM (backend) -- increase productivity -- less use of manual method -- reduce time consumption

### What is Prisma?

- prisma is an open-source database toolkit that simplifies database access and management.
- prisma is next-generation ORM(object-relational-mapping).
- prisma is very powerful & industry standard.
- good for small and mid-level projects.

### Why Prisma?

- Prisma supports multiple popular databases like MySQL, SQLite, MSSQL, PostgreSQL, and also with mongoDB (NoSQL),
  providing developers with flexibility when choosing the database that best fits their project's requirements.

### Should you use Prisma?

- if you are building a server-side application that talks to database.
- you care about productivity and developer experience.
- you are working in a team.
- you want a tool that holistically covers your database workflows
- you value type-safety
- you want an ORM with a transparent development process, proper maintenance & support.
- you want to be part of an awesome community.

### Components of Prisma: 3 components

- prisma client: auto-generated and type-safe query builder for Node.js & typeScript
- Prisma Migrate: a migration system for managing changes to your database schema.
- prisma studio: a graphical user interface (GUI) for viewing and editing data in your database.

- prisma's main goal is to make application developers more productive when working with database. considering the
  tradeoff between productivity and control again, this is how prisma fits in:

### Limitations of Prisma

- might not perform well for complex quires, in that case we can use RAW SQL queries.
- serverless deployment is complex, as prisma ships with extra engines.
- doesn't use database level joins, instead uses multiple queries and joins the data in it's RUST engine.

**2 Mar, 24**

## 55-2 Project Setup for Prisma

- [Prisma.io](https://www.prisma.io/)
- (https://www.prisma.io/docs/getting-started)
- (https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch/relational-databases-typescript-postgresql)

- steps:

  - create a directory
  - run the following commands:

    ```
    yarn init -y
    ```

    ```
    yarn add prisma typescript tsx @types/node --save-dev
    ```

    ```
    npx tsc --init
    ```

    <br> modify tsconfig.json file --- set root directory

    ```bash
    npx prisma
    ```

    <br> copy paste schema from Using Prisma Migrate to schema.prisma file

    ```
    npx prisma migrate dev --name init
    ```

    <br> it will convert this schema to query, a new folder `migrations` within prisma folder will be created.

## 55-3 Prisma Extension, Schema Establishment, and ts-node-dev installation

- create post schema in schema.prisma file

- to convert in SQL:

```
npx prisma migrate dev
```

- if you want you may delete migration folder and run command to get new migration folder

- [ts node dev](https://www.npmjs.com/package/ts-node-dev)

```
yarn add ts-node-dev --dev
```

- To convert prisma schema to SQL for database
- then give a table name

**3 Mar, 25 & 4 Mar, 25**

## 55-4 Inserting Data into the Database and Retrieving All Records

- modify package.json file

- add as script in package.json file:

```
ts-node-dev --respawn --transpile-only server.ts
```

- package.json file dependencies:

```
npm install @prisma/client
```

- prisma client provides type safety

- prisma provides 3 components: prisma client (type safety), prisma studio (provides GUI to manage data), and prisma migrate (migration -- convert from model to query language)

```
npx prisma studio
```

- create and find operation in prisma

- prisma client -- type safety
- prisma migrate -- model to query language
- prisma studio -- provide a GUI 

**4 Mar, 25**

## 55-5 Reading Records and Executing Queries

- to run the project:

```
yarn dev
```

```
npx prisma studio
```

- create find.ts
- modify package.json file script, dev property

<!--
{
  "name": "prismamastery",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT",
  "scripts": {
    "dev": "ts-node-dev --respawn --transpile-only src/find.ts"
    // "dev": "ts-node-dev --respawn --transpile-only src/index.ts"
  },
  "dependencies": {
    "@prisma/client": "^6.4.1",
    "@types/node": "^22.13.8",
    "prisma": "^6.4.1",
    "tsx": "^4.19.3",
    "typescript": "^5.8.2"
  },
  "devDependencies": {
    "ts-node-dev": "^2.0.0"
  }
}

 -->

**6 Mar, 25**

## 55-6 Creating Multiple Records and Understanding Differences between create and createMany

- create create.ts
- modify package.json file script, dev property

## 55-7 Updating Records: Single and Multiple Record Updates and Their Distinctions

- create update.ts
- modify package.json file script, dev property

## 55-8 Deleting Records: Single and Multiple Deletion Operations and Their Variations

- create delete.ts
- modify package.json file script, dev property

## 55-9 Upsert Operations and Select Queries

- `upsert` : if data is available the update it, and if data is not available then delete it

## 55-10 Implementing Pagination and Sorting in Prisma

- `offset pagination`: offset pagination uses skip and take to skip a certain number of results and select a limited range.

- `Cursor based pagination`: cursor-based pagination uses cursor and take to return a limited set of results before or after a given cursor.