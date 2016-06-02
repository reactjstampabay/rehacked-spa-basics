![ReactJS Tampa Bay Logo](http://photos1.meetupstatic.com/photos/event/c/7/6/6/global_449391046.jpeg)

### [ReactJS Tampa Bay](http://www.meetup.com/ReactJS-Tampa-Bay/)

# ReHacked (June 8, 2016): React SPA Basics

Welcome to ReHacked! By the end of this lab, you will have:

* Created a "ground up" React SPA using Webpack and Babel (for JSX and ES2015 support)
* Implemented some React components
* Implemented a simple routing system
* Implemented a service to talk to a Web API for simple authentication

# PreHacked

## Suggested Tools

1. [Atom](https://atom.io/) or [WebStorm](https://www.jetbrains.com/webstorm/)

1. [SourceTree](https://www.sourcetreeapp.com/) (If not using WebStorm)

## Setup Instructions

1. Install [git](https://git-scm.com/downloads)

1. Install [Node Version Manager](https://github.com/creationix/nvm) ([Windows NVM](https://github.com/coreybutler/nvm-windows))

1. Install Node 4.4.5 (using `nvm install 4.4.5`)

1. Execute `nvm alias default 4.4.5`

1. Execute `npm install -g npm3`

1. Signup for a [Firebase](https://firebase.com) account

# ReHacked
  
## Initialize NPM and git

1. `mkdir rehacked-spa-basics && $_`  

1. `echo "# rehacked-spa-basics" >> README.md`

1. `printf "# node\nnode_modules\n\n# IDE\n.idea\n\n# webpack\nbuild" >> .gitignore`

1. `npm init`

#### add global dependencies

1. `npm3 install -g webpack webpack-dev-server`

#### add project dependencies

1. `npm3 install react react-dom react-router isomorphic-fetch material-design-lite classnames babel-polyfill babel-preset-es2015 babel-preset-react --save`

#### add dev dependencies

1.  `npm3 install babel-core babel-loader css-loader extract-text-webpack-plugin file-loader node-sass null-loader open-browser-webpack-plugin sass-loader source-map-loader static-loader style-loader webpack webpack-dev-server --save-dev`

#### create repo and push up changes

1. `git init`

1. `git add .`

1. `git commit -m "initial commit"`

1. Create new repo on GitHub

1. `git remote add origin https://github.com/reactjstampabay/rehacked-spa-basics.git`

1. `git push -u origin master`

## Add Webpack and Environment config

1. `touch webpack.config.js`

1. Copy contents of pre-defined [webpack config](https://gist.github.com/johnrhampton/82b5d0cebfb4b02645c7a9c1698330d8)

1. `mkdir config && cd $_ && touch local.js && cd -`

1. Copy contents of pre-defined [local environment config](https://gist.github.com/johnrhampton/76f663969a11e89865b33113ed4eda6e)

## Add baseline components and start app

1. `cd .. && mkdir src && cd $_ && touch app.js && touch index.html` 

1. Copy contents of pre-defined [index.html](https://gist.github.com/johnrhampton/9b15891913dcd04ca15c033311c712a4)

1. Copy contents of pre-defined [app.js](https://gist.github.com/johnrhampton/cc0e6a04cd08535b640ae99a20913e4f)

1. Create `StartScreen/index.js` - `mkdir -p src/components/StartScreen && cd $_ && touch index.js && cd -`

1. Create `Dashboard/index.js` - `mkdir -p src/components/Dashboard && cd $_ && touch index.js && cd -`

1. Add basic class with render function that returns _hello from react_ div

1. Start app - `webpack-dev-server --config webpack.config.js --content-base build/ --inline --hot`

## Add Login component with loading

1. Create `Login/index.js` - `mkdir -p src/components/Login && cd $_ && touch index.js && cd -`

1. Create `Loading/index.js` - `mkdir -p src/components/Loading && cd $_ && touch index.js && cd -`

1. Copy contents of pre-defined [Login Component](https://gist.github.com/johnrhampton/1df0ad69a2b3aacc6a42626cfe553bf7)

1. Copy contents of pre-defined [Loading Component](https://gist.github.com/johnrhampton/7259212dec666bf656bc8c457ebf3199)

1. Import Login component StartScreen and replace _hello from react_ div

1. Add constructor, state, and other required functions to StartScreen component.  Pass required attributes to <Login /1.
1.1. Ensure to wire up _componentHandler.upgradeDom();_ in appropriate lifecycle events (didMount, didUpdate)

1. We are focusing on Login, and will circle back to Register if we have time - demo Postman

## Add SCSS

1. Create `main.scss` - `mkdir -p src/assets/styles && cd $_ && touch main.scss && cd -`

1. Uncomment Stylesheets require in `app.js`

1. Copy contents of pre-defined [main.scss](https://gist.github.com/johnrhampton/336ad7b3d903ac063e94e3d7a9f4accb)

## Dev Tools

1. Add [React Dev Tools Chrome Extension](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi) 

1. Under React tab - find StartScreen component and demonstrate setting state _loading = true_

## Simple Validation

1. Add showSnackbar function

1. Add email/password check in _handleLogin_ 

## Add User Service and Common Environment Config

1. Create `user.js` - `mkdir -p src/common/services && cd $_ && touch user.js && cd -`

1. Create `environment.js` - `mkdir -p src/common/constants && cd $_ && touch environment.js && cd -`

1. Export API_PATH from `local.js` - `export const ENVIRONMENT = { API_PATH: '' };`

1. Create `endpoints.js` - `mkdir -p src/common/constants && cd $_ && touch endpoints.js && cd -`

1. Export USER const - `export const USER = { LOGIN: '/user/login' };`

1. Import API_PATH and USER in `user.js`

1. Add `login` function to `user.js`

#### todo: finish login function and add gist for user service, finish wiring up login in StartScreen, add StartScren gist

#### todo: create gist for Dashboard (MDL template?)