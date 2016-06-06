![ReactJS Tampa Bay Logo](https://avatars2.githubusercontent.com/u/18738421?v=3&s=200)

# ReHacked (June 8, 2016): React SPA Basics
### By [ReactJS Tampa Bay](http://www.meetup.com/ReactJS-Tampa-Bay/)

Welcome to ReHacked! By the end of this lab, you will have:

* Created a "ground up" React SPA using Webpack and Babel (for JSX and ES2015 support)
* Implemented some React components
* Implemented a simple routing system
* Implemented a service to talk to a Web API for simple authentication
* Deployed the React SPA to Firebase

# [PreHacked](#prehacked)

## Suggested Tools

1. [Atom](https://atom.io/) or [WebStorm](https://www.jetbrains.com/webstorm/)
  - [terminal-plus for Atom](https://atom.io/packages/terminal-plus)

1. [SourceTree](https://www.sourcetreeapp.com/) (If not using WebStorm)

## Setup Instructions

1. Signup for a [GitHub](https://github.com) account

1. Install [git](https://git-scm.com/downloads)

1. Install [Node Version Manager](https://github.com/creationix/nvm) ([Windows NVM](https://github.com/coreybutler/nvm-windows))

1. Install Node 4.4.5 (using `nvm install 4.4.5`)

1. Execute `nvm alias default 4.4.5`

1. Execute `npm install -g npm3`

1. Signup for a [Firebase](https://firebase.com) account

# ReHacked
  
## Initialize NPM and git

1. Go to a directory of your choice and create a `rehacked-spa-basics` folder
  - **bash:** `mkdir rehacked-spa-basics && $_`

1. Create a `README.md` file 
  - **bash:** `echo "# rehacked-spa-basics" >> README.md`

1. Create a `.gitignore` file 
  - **bash:** `printf "# node\nnode_modules\n\n# IDE\n.idea\n\n# webpack\nbuild" >> .gitignore`

1. Execute `npm init`
  - **name**: rehacked-spa-basics
  - **version**: 1.0.0
  - **description**: A React SPA with basic functionality
  - **entry point**: ./src/app.js
  - **test command**: <Enter>
  - **git repository**: <Enter>
  - **keywords**: <Enter>
  - **author**: [Enter your name]
  - **license**: <Enter>

#### add global dependencies

1. Execute `npm3 install -g webpack webpack-dev-server`

#### add project dependencies

1. Execute `npm3 install react react-dom react-router isomorphic-fetch material-design-lite classnames babel-polyfill babel-preset-es2015 babel-preset-react --save`

#### add dev dependencies

1. Execute  `npm3 install babel-core babel-loader css-loader extract-text-webpack-plugin file-loader node-sass null-loader open-browser-webpack-plugin sass-loader source-map-loader static-loader style-loader webpack webpack-dev-server --save-dev`

#### create repo and push up changes

1. Execute `git init`

1. Execute `git add .`

1. Execute `git commit -m "initial commit"`

1. Create a new _empty_ repo on GitHub

1. Execute `git remote add origin [https link to your Git repo]`

1. Execute `git push -u origin master`

## Add Webpack and Environment config

1. Create a `webpack.config.js` file 
  - **bash:** `touch webpack.config.js`

1. Copy contents of pre-defined [webpack config](https://gist.github.com/johnrhampton/82b5d0cebfb4b02645c7a9c1698330d8)

1. Create a `config` directory and a `local.js` file in it 
  - **bash:** `mkdir config && cd $_ && touch local.js && cd -`

1. Copy contents of pre-defined [local environment config](https://gist.github.com/johnrhampton/76f663969a11e89865b33113ed4eda6e) to `local.js`

## Add baseline components and start app

1. Create an `index.html` and `app.js` for your SPA 
  - **bash:** `mkdir src && cd $_ && touch app.js && touch index.html` 

1. Copy contents of pre-defined [index.html](https://gist.github.com/johnrhampton/9b15891913dcd04ca15c033311c712a4) to `index.html`

1. Copy contents of pre-defined [app.js](https://gist.github.com/johnrhampton/cc0e6a04cd08535b640ae99a20913e4f) to `app.js`

1. Create a `components` subdirectory under the `src` folder.

1. Create `StartScreen/index.js` under `components`
  - **bash (from the root of the project):** `mkdir -p src/components/StartScreen && cd $_ && touch index.js && cd -`
  
1. Add basic class with render function that returns _hello from react_ div

1. Create `Dashboard/index.js` 
  - **bash (from the root of the project):** `mkdir -p src/components/Dashboard && cd $_ && touch index.js && cd -`

1. Add basic class with render function that returns _My Dashboard_ div

1. Start app by going to the root of your repo and executing `webpack-dev-server --config webpack.config.js --content-base build/ --inline --hot`

## Add Login component with loading

1. Create `Login/index.js` 
  - **bash (from the root of the project):** `mkdir -p src/components/Login && cd $_ && touch index.js && cd -`

1. Create `Loading/index.js` 
  - **bash (from the root of the project):** `mkdir -p src/components/Loading && cd $_ && touch index.js && cd -`

1. Copy contents of pre-defined [Login Component](https://gist.github.com/johnrhampton/1df0ad69a2b3aacc6a42626cfe553bf7)

1. Copy contents of pre-defined [Loading Component](https://gist.github.com/johnrhampton/7259212dec666bf656bc8c457ebf3199)

1. Import Login component in StartScreen and replace _hello from react_ div

1. Add constructor, state, and other required functions to StartScreen component.  
    1. Pass required attributes to `<Login />`
        
          ```javascript
            <Login loading={this.state.loading} 
                   email={this.state.email} 
                   password={this.state.password} 
                   handleFieldChange={this._handleFieldChange}  
                   handleLogin={this._handleLogin}/>
          ```
        1. Ensure to wire up _componentHandler.upgradeDom();_ in appropriate lifecycle events (didMount, didUpdate)

1. We are focusing on Login, and will circle back to Register if we have time - demo Postman

## Add SCSS

1. Create `main.scss` 
  - **bash (from the root of the project):** `mkdir -p src/assets/styles && cd $_ && touch main.scss && cd -`

1. Uncomment Stylesheets require in `app.js`

1. Copy contents of pre-defined [main.scss](https://gist.github.com/johnrhampton/336ad7b3d903ac063e94e3d7a9f4accb)

## Dev Tools

1. Add [React Dev Tools Chrome Extension](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi) 

1. Under React tab - find StartScreen component and demonstrate setting state _loading = true_

## Simple Validation

1. Add `_showSnackBar` function
  - Pre-defined [StartScreen/index.js](https://gist.github.com/johnrhampton/e6dea5e41cf0a64f10d8b728e6beea55)

1. Add email/password check in _handleLogin_ 

## Add User Service and Common Environment Config

1. Create `user.js` 
  - **bash (from the root of the project):** `mkdir -p src/common/services && cd $_ && touch user.js && cd -`

1. Create `environment.js` 
  - **bash (from the root of the project):** `mkdir -p src/common/constants && cd $_ && touch environment.js && cd -`

1. Export API_PATH from `local.js` - `export const ENVIRONMENT = { API_PATH: '' };`

1. Create `endpoints.js` 
  - **bash (from the root of the project):** `mkdir -p src/common/constants && cd $_ && touch endpoints.js && cd -`

1. Export USER const - `export const USER = { LOGIN: '/user/login' };`

## Build User Login

1. Import 'isomorphic-fetch', {ENVIRONMENT} and {USER} in `user.js`

1. Export `login` function in [`user.js`](https://gist.github.com/johnrhampton/2eaa69eed860d5f4220a3fafb5b62e36) 

1. Import `* as UserService` in `StartScreen/index.js`

1. Invoke `UserService.login` on validation `_handleLogin`

1. Set app state to display loading during login process

1. Add stringify'd `USER_PROFILE` to localStorage on success, invoke `_showSnackBar` on login error (incorrect email or pw)

1. Log parsed `USER_PROFILE` to console to demonstrate API response payload

## Navigate to Dashboard

1. Import {hashHistory} from `react-router`

1. Add push to `/dashboard` on login success

1. Navigate back to Login and Forward to Dashboard - `delete localStorage['USER_PROFILE']` - can no longer nav forward

## Give Dashboard some style

1. Create `assets/style/dashboard.scss`

1. Copy contents of pre-defined [dashboard.scss](https://gist.github.com/johnrhampton/d1fadde1292bac10c28f4920d48dce72)

1. @Import `./dashboard.scss` in `main.scss`

1. Copy contents of pre-defined [`Dashboard/index.js`](https://gist.github.com/johnrhampton/5002d240cd5ae32bcbdfa6814a1090f2)

## Deploy to Firebase

1. Build SPA bundle with Webpack - `webpack --config webpack.config.js`

1. Open the [Firebase Console](https://console.firebase.google.com/?pli=1)

1. Create a new Firebase project

1. Click on `Hosting` in the left sidebar
 
1. Install firebase-tools - `npm install -g firebase-tools`

#### Login and Initialize Firebase from your project's directory

1. `firebase login` - a browser will open to authenticate with Google

1. `firebase init` - select **Hosting**, hit spacebar next to **Database** to de-select
  - `build` for your public directory
  - `Y` for SPA
  - Select your newly created project on Firebase

1. `firebase deploy`

1. Open the deployed app and login