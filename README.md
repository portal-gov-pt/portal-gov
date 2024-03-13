# Open Components

This Project is part of a Single Digital Portal in Portugal The PDUN - Portal Digital Unico Nacional to publish open components

## Open Components

### Portal Header

### Portal Footer

### Feedback

### Maps of public services



## Available Scripts

### Build the library

```
npm run rollup
```

### Publish the library

```
npm publish
```

### Run tests

```
npm run test
```

### Run storybook locally

```
npm run storybook
```

### Build storybook

```
npm run build-storybook
```

## Tutorial

1. [Introduction](#introduction)
1. [Prerequisites and Setup](#prerequisites-and-setup)
1. [Creating Components](#creating-components)
1. [Adding Typescript](#adding-typescript)
1. [Adding Rollup](#adding-rollup)
1. [Building Your Library](#building-your-library)
1. [Publishing Your Library](#publishing-your-library)
1. [Using Your Library](#using-your-library)
1. [Adding CSS](#adding-css)
1. [Optimizing](#optimizing)
1. [Adding Tests](#adding-tests)
1. [Adding Storybook](#adding-storybook)
1. [Adding SCSS](#adding-scss)
1. [Wrapping Up](#wrapping-up)

## Introduction

Sample

```bash
npm install @portal-gov-pt/portal-components
```

```jsx
import { PortalHeader, PortalFooter } from '@portal-gov-pt/portal-components';

const MyApp = () => {
  return (
    <div>
      <PortalHeader />
      <MyCustomContent />
      <PortalFooter />
    </div>
  )
}
```

## Prerequisites and Setup

This project assumes you are familiar with and have installed:

* Code editor / IDE (this tutorial uses VS Code but any IDE will work)
* NPM (NPM is installed when you install Node.js on your machine)
* Installing packages (presume you know how to add packages to a Javascript project with `npm install`)
* Bash terminal (or another terminal you are comfortable with for running commands)
* Git (we will be creating a git repository on our machine and publishing it to Github, though all instructions will be provided on how to follow along)
* React (how to be using JSX)
* Typescript (how to create an object interface with simple properties)

## Using Portal Components Library

Now that your library is live, you'll want to use it!  

Note that the instructions for using your library are slightly different if you published to a _private_ repository.  Everyone (aside from your own machine) who tries to import it is going to get a _404 Not Found_ error if they are not authorized.  

Those users also need to add a `~/.npmrc` file with the same information.  To be more secure however you can provide those users with an access token that has only **read privileges**, not write.  

_(From this point onward we will presume you have completed that step, or are working with a public repository.)_

Since we have created a component library using React and Typescript, we are presuming that the consumers of our library will be using those tools as well.  Technically all of our type files `(.d.ts)` are supplemental: meaning they are simply ignored if working with standard Javascript, so it's not necessary to use Typescript to use our library.  The types are simply there if desired.  

For our example we will use it however so that we can confirm that they are working properly.  We will initialize a React app using one of the most popular and simple methods: [Create React App](https://reactjs.org/docs/create-a-new-react-app.html).

Run the following command in a **new directory**:

_(Remember we are simulating other users downloading and installing our library, so this project should be completely separate from the library itself)_

```bash
npx create-react-app my-app --template typescript
```

Open the new `my-app` directory that is created and run:

```bash
npm run start
```

Confirm that you are able to open and load the default application screen on `localhost:3000` (or whatever port it opens on).

Now comes the test for our library.  From the root directory of your new `my-app` project, run the following command:

```bash
npm install @portal-gov-pt/portal-components
```

So for my project for example its: `npm install @alexeagleson/template-react-component-library`

Presuming your tokens and configuration are set up properly, everything will install correctly _(if there are any issues, revisit the example for the `~/.npmrc` config.)_

Now open the `my-app` project in your IDE of choice (VS Code for example) and navigate to the `src/App.tsx` file. 

When you go to add a `<Button />` component, if your editor supports import auto complete (`ctrl/cmd + .` for VS Code) then you will see it automatically recognize thanks to Typescript that our library exports that button.  

Lets add it!  The simplest example to update `src/App.tsx` is:

`src/App.tsx`
```tsx
import React from "react";
import { PortalHeader, PortalFooter } from '@portal-gov-pt/portal-components';

function App() {
      <PortalHeader />
      <h1>Basic Portal Content</h1>
      <PortalFooter />
}

export default App;
```
