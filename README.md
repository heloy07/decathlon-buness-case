This is a small page created as a task for a recruitment process at Decathlon.
The idea is a small carousel with photos from people who shared their thoughts about the company and 
rated their experience.

---
Live demo: https://keen-nightingale-531d4f.netlify.app/
# Built using Svelte

This project was fully built with Svelte and uses vtmn/css which is CSS library built on top of Twailwind
and provides elements of the Decathlon Design


*Note that you will need to have [Node.js](https://nodejs.org) installed.*


## Get started

Install the dependencies...

```bash
cd decathlon-business-case
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `sirv` commands in package.json to include the option `--host 0.0.0.0`.

If you're using [Visual Studio Code](https://code.visualstudio.com/) we recommend installing the official extension [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode). If you are using other editors you may need to install a plugin in order to get syntax highlighting and intellisense.

## Building and running in production mode

To create an optimised version of the app:

```bash
npm run build
```

You can run the newly built app with `npm run start`. This uses [sirv](https://github.com/lukeed/sirv), which is included in your package.json's `dependencies` so that the app will work when you deploy to platforms like [Heroku](https://heroku.com).


## Structure

The project has 4 components aside from App.svelte:
Banner,Carousel,Rating,Icon
The first three are directly imported to App.svelte whereas Icon describe one Icon of the Rating component.
In the data folder we can find two js files. They're supposed to represent some data base given that it was not required for this task to implement any sort of backend.
