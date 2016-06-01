# rehacked-spa-basics
The codebase for the first ReHacked lab -- React SPA basics

The steps below are built with OS X in mind

## Prerequisites
> [git](https://git-scm.com/downloads)

> [Node Version Manager](https://github.com/creationix/nvm) ([Windows NVM](https://github.com/coreybutler/nvm-windows))

> Node 4.4.5 (using `nvm install 4.4.5`)

> `nvm alias default 4.4.5`

> `npm install -g npm3`
  
## Initialize NPM and git
> `mkdir rehacked-spa-basics`  

> `cd rehacked-spa-basics`

> `echo "# rehacked-spa-basics" >> README.md`

> `printf "# node\nnode_modules\n\n# IDE\n.idea\n\n# webpack\nbuild" >> .gitignore`

> `npm init`

#### add global dependencies
> `npm3 install -g webpack webpack-dev-server`

#### add project dependencies
> `npm3 install react react-dom react-router material-design-lite classnames babel-polyfill babel-preset-es2015 babel-preset-react --save`

#### add dev dependencies
>  `npm3 install babel-core babel-loader css-loader extract-text-webpack-plugin file-loader node-sass null-loader open-browser-webpack-plugin sass-loader source-map-loader static-loader style-loader webpack webpack-dev-server --save-dev`

#### create repo and push up changes
> `git init`

> `git add .`

> `git commit -m "initial commit"`

> Create new repo on GitHub

> `git remote add origin https://github.com/reactjstampabay/rehacked-spa-basics.git`

> `git push -u origin master`

## Add Webpack and Environment config
> `touch webpack.config.js`

> Copy contents of pre-defined [webpack config](https://gist.github.com/johnrhampton/82b5d0cebfb4b02645c7a9c1698330d8)

> `mkdir config && cd $_ && touch local.js`

> Copy contents of pre-defined [local environment config](https://gist.github.com/johnrhampton/76f663969a11e89865b33113ed4eda6e)

## Add baseline components and start app

> `cd .. && mkdir src && cd $_ && touch app.js && touch index.html` 

> Copy contents of pre-defined [index.html](https://gist.github.com/johnrhampton/9b15891913dcd04ca15c033311c712a4)

> Copy contents of pre-defined [app.js](https://gist.github.com/johnrhampton/cc0e6a04cd08535b640ae99a20913e4f)

> Create `StartScreen/index.js` and `Dashboard/index.js` - add basic Component that returns div

> `webpack-dev-server --config webpack.config.js --content-base build/ --inline --hot`

## Add Login component

> Create `Login/index.js` and `Loading/index.js`

> Copy contents of pre-defined [Login Component](https://gist.github.com/johnrhampton/1df0ad69a2b3aacc6a42626cfe553bf7)

> Copy contents of pre-defined [Loading Component](https://gist.github.com/johnrhampton/7259212dec666bf656bc8c457ebf3199)

> Import Login component StartScreen and replace _hello from react_ div

> Add constructor, state, and other required functions to StartScreen component.  Pass required attributes to <Login />
>> Ensure to wire up _componentHandler.upgradeDom();_ in appropriate lifecycle events (didMount, didUpdate)

## Add SCSS

> Create `main.scss` - `mkdir -p src/assets/styles && cd $_ && touch main.scss`

> Uncomment Stylesheets require in `app.js`

> Copy contents of pre-defined [main.scss](https://gist.github.com/johnrhampton/336ad7b3d903ac063e94e3d7a9f4accb)

## Dev Tools

> Add [React Dev Tools Chrome Extension](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi) 

> Under React tab - find StartScreen component and demonstrate setting state _loading = true_