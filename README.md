# Introduction
For products involving deliveries, ride-hailing, ecommerce, and logistics, it is important include an optimized last-mile delivery tracking experience. NextBillion.ai provides a set of mapping and location-based service APIs and SDKs that allow developers to easily integrate maps and last mile tracking into the product.

In this example, we will go through the steps to solve the classic Vehicle Routing Problem (VRP) with the NextBillion API and SDK using ReactJS + TypeScript.

By the end of this tutorial you should be able to;

```
will be filled in by the project's end
```

# Prerequisite

To follow this tutorial you must have
1.  Basic understanding of ReactJS. [ReactJS Docs](https://reactjs.org/docs/getting-started.html) are a great way to start learning React.
2. Basic knowledge about TypeScript and types
3. Have `npm (Node Package Manager)` and `nodejs` installed on your machine
4. NextBillion API host url and API key. Create a NextBillion account by visiting the [Get API key page](https://doc.maps.nextbillion.io/docs/get-an-api-key) in NextBillion docs.
 
# Setup

Now that we have our API Key, we're ready to begin. 

Let's first create a ReactJS project with TypeScript support using the following command. 
Change directory into the folder that you like to keep your projects in, and run the following command in that directory

```shell
npx create-react-app grocery-dispatch --template typescript
```

We are using `npx` here; if you do not have it installed you can install it globally by running the following command 
```
sudo npm i -g npx
```

I have named by project `grocery-dispatch`, you can use your favourite string of characters.

After the dependencies are installed and the project is installed, changed directory into the project and run start the development server

```
cd gorcery-dispatch
npm start
```

Visit http://localhost:3000 from your browser and you should be able to see the default React application running.

Let us now install `NextBillion SDK` and some other helpful packages into our application.

```
# Installing NextBillion SDK
npm install nbmap-gl
```

```
# Installing styled-components for styling
npm install styled-components
```

You can use plain CSS some other styling library if you want.
You can read about `styled-components` [here](https://styled-components.com/docs)


## Adding Environment variables

Create a file named `.env` in your project root, we will be storing our API keys and other secrets in this file. 

```
Note: Make absolutely sure to add .env in you .gitignore. You never want to push 
your secrets to a public repository
```

Now, in order for react to recognize your environment variable, it must be preceded by `REACT_APP_`

I'll be naming my key as `REACT_APP_NEXT_BILLION_API_KEY`. You can use whatever name you like just make sure to prepend `REACT_APP_` to it.


## Getting started with React

First of all, we'll be deleting all the boilerplate files that the React CLI has created for us. We only want `App.tsx`, `index.tsx` and `react-app-env.d.ts` in our `src` folder.

Make sure to remove all the imports in `App.tsx` and `index.tsx` that import the now deleted files.

This is what my project looks like after purging the boilerplate files

```
├── .env
├── .gitignore
├── package.json
├── package-lock.json
├── public
│   ├── favicon.ico
│   ├── index.html
│   ├── logo192.png
│   ├── logo512.png
│   ├── manifest.json
│   └── robots.txt
├── README.md
├── src
│   ├── App.tsx
│   ├── index.tsx
│   └── react-app-env.d.ts
└── tsconfig.json
```
