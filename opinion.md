## io-ts

It is used for typescript validation for input data received from some API endpoint or database.
It is used to validate input data using types in typescript.

Since the user can enter any kind of data, we need a method to validate that data. We define an interface using decoder interface that represents the format or exact structure of the input data. Then we can validate the input data by comparing it against our defined type. The decode function returns the successfully decoded object if input data exactly matches the type. Otherwise it returns the Error. It uses Either type to return either validated object or error. It is straightforward to use.


## React

React is a JavaScript library for building UI components.
Each component is a function that returns custom, reusable HTML elements and handles data using state and props. We can maintain state using hooks. We need to register event handlers for the specific events and write handler functions to handle events and change state accordingly.

It is much more organized and structured than using just HTML,CSS and JS.
I am very comfortable in writing applications in React. I understand different aspects of it clearly.

## React Router

It is used to navigate from one page to another in our React app.
In most basic form, we use Route , Link and Switch elements and many hooks are also provided.


## Next.js

It is still just React with added features.

  - Next.js can pre-render pages, which are static, at build time, instead of at client-side. Pre-rendering can result in faster page display and SEO.

    I think if we build it on client side, it will be slow because first JS will load then execute and then page is displayed, so searches will not be able to show our page in results as its content is not yet available.

  - We use Static Generation for static pages and use Server-side Rendering for others.

  - We can also use client side rendering for frequently updating data. Static parts of the page can be pre-rendered using static generation and then fetch the data on the client side and display it.
  We can show **"loading state" or "skeleton"** while page loads.We can use React hook for data fetching called **SWR** to update cache and display updated data to the user, otherwise updated data is not shown immediately on the page until we refresh the page. This is a big problem while using async/await database CRUD operations

  - The file system itself acts as a Router.
  - Any file in /pages/api/ becomes an API route.
    (No need to use Route, Switch etc)

It took me a while to understand the concept of client side rendering and server side rendering and API endpoints. But now I understand it better.


## Blitz.js

It is built on top of the next.js
It is in beta version

It has many built in features like “Zero-API” data layer and everything end-to-end from the database to the frontend.

By default, Blitz uses Prisma 2 and a local SQLite database. If we want to use PostgreSQL or any other, we can configure it using steps given in documentation.

**It has 2 tables predefined: User and Session. All this is provided in "db" folder of the app.**

Basic login and sign up using email and password is provided by default which is completely functional. It uses hashed passwords and rehashes passwords at intervals. All this is provided in "auth" folder of the app. In documentation, it is specified that it uses SuperTokens library but it is not visible in any automatically generated code in the app.

Blitz provides a handy command called generate for scaffolding out boilerplate code.

>     **blitz generate all todo text:string completed**

It generates "todo" model automatically and generates following files:

CREATE    app/todo/pages/todo/index.tsx
CREATE    app/todo/pages/todo/new.tsx
CREATE    app/todo/pages/todo/[todoId]/edit.tsx
CREATE    app/todo/pages/todo/[todoId].tsx
CREATE    app/todo/components/TodoForm.tsx
CREATE    app/todo/queries/getTodos.ts
CREATE    app/todo/queries/getTodo.ts
CREATE    app/todo/mutations/createTodo.ts
CREATE    app/todo/mutations/deleteTodo.ts
CREATE    app/todo/mutations/updateTodo.ts

All these files contain boilerplate code with types. I just have to insert my program logic in these files.

Initially, I was overwhelmed by the amount of  auto-generated files.
I feel that the file structure is too long to find a particular file.
Many features are automatically provided and it takes time to understand whats going on in the application.

The CRUD operations are written in folders: **queries(GET)** and **mutations(create, update,delete,upsert)**.


I had to write the same code that i wrote while using React but to do that i had to first search the specific file to write corresponding
part of the code.

**We can use refetch() function and setQueryData() returned by useQuery() hook instead of using SWR.**

I think it is extremely simple to develop applications in blitz as we can just concentrate on writing the main application logic.




