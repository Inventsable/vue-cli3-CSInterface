# vue-cli-test

Working example of `CSInterface` inside a vue-cli build, updated from [vue-cli-3-CEP](https://github.com/Inventsable/vue-CLI-3-for-CEP) with only prerequisite being NodeJS. 

## In your terminal:

1) `npm install -g @vue/cli` (only need to do this once and never again)
2) `npm install -g @vue/cli-init` (only need to do this once and never again)
3) `vue init webpack-simple (name of project here)`
4) Follow the terminal prompts for your template
5) It prompts you to `cd (name of project here)`
6) `npm install`
7) (Might not be needed) `npm run build` 
8) `npm run dev`
9) Ready! Now paste in a CSXS folder (check the readme to see how to enable live reloading and nodejs for `manifest.xml`) and .debug file, set up your two index files, make sure you have a PORT in `webpack.config.js` like [linked here](https://github.com/Inventsable/vue-cli3-CSInterface/blob/master/webpack.config.js#L52), and finally [add CSInterface to `App.vue`](https://github.com/Inventsable/vue-cli3-CSInterface/blob/master/src/App.vue#L19) (or use `import`/`require` methods). Or just copy/paste the files from this repo into yours and hack your way through.

## Other important notes:

* You must run the `npm run dev` command prior to opening your app (at least for AI) if you want hot-reloading to work.

* See `./CSXS/` for notes on `manifest.xml` file for nodeJS.

* See `index-dev.html` and `index.html`. `index-dev.html` is pointed to in `manifest.xml`, which itself contains the PORT: parameter to `index.html` from `webpack.config.js` file (line #52). `index.html` can contain any number of external scripts like `CSInterface.js`, though this likely isn't good practice.