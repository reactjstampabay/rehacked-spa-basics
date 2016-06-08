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
    - [Windows 10 User Instructions for terminal-plus](https://github.com/jeremyramin/terminal-plus/issues/15#issuecomment-144618245)

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

1. Copy contents of pre-defined [webpack config](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/webpack.config.js)

1. Create a `config` directory and a `local.js` file in it 
  - **bash:** `mkdir config && cd $_ && touch local.js && cd -`

1. Copy contents of pre-defined [local environment config](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/config/local.js) to `local.js`

## Add baseline components and start app

1. Create an `index.html`, `app.js`, and `dependencies.js` for your SPA 
  - **bash:** `mkdir src && cd $_ && touch app.js && touch index.html && touch dependencies.js` 

1. Copy contents of pre-defined [index.html](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/src/index.html) to `index.html`

1. Copy contents of pre-defined [app.js](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/src/app.js) to `app.js`

1. Copy contents of predefined [dependencies.js](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/src/dependencies.js)

1. Create a `components` subdirectory under the `src` folder.

1. Create `StartScreen/index.js` under `components`
  - **bash (from the root of the project):** `mkdir -p src/components/StartScreen && cd $_ && touch index.js && cd -`
  
1. Add basic class with render function that returns _hello from react_ div

1. Create `Dashboard/index.js` 
  - **bash (from the root of the project):** `mkdir -p src/components/Dashboard && cd $_ && touch index.js && cd -`

1. Add basic class with render function that returns _My Dashboard_ div

1. Start app by going to the root of your repo and executing one of the following: 
  - *nix Environments: `webpack-dev-server --config webpack.config.js --content-base build/ --inline --hot`
  - Windows Environments `webpack-dev-server --progress --colors --inline --content-base build/`

## Add User Service and Common Environment Config

1. Create `src/common/services/user.js` 
  - **bash (from the root of the project):** `mkdir -p src/common/services && cd $_ && touch user.js && cd -`

1. Create `src/common/constants/environment.js` 
  - **bash (from the root of the project):** `mkdir -p src/common/constants && cd $_ && touch environment.js && cd -`

1. Export API_PATH from `local.js` - `export const ENVIRONMENT = { API_PATH: '' };`

1. Create `src/common/constants/endpoints.js` 
  - **bash (from the root of the project):** `mkdir -p src/common/constants && cd $_ && touch endpoints.js && cd -`

1. Export USER const - `export const USER = { LOGIN: '/user/login' };`

## Build User Login

1. Import 'isomorphic-fetch', {ENVIRONMENT} and {USER} in `user.js`

1. Export `login` function in [`/src/common/services/user.js`](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/src/common/services/user.js) 

1. Import `* as UserService` in `StartScreen/index.js`

## Add Login component with loading and utilize UserService

1. Create `src/components/Login/index.js` 
  - **bash (from the root of the project):** `mkdir -p src/components/Login && cd $_ && touch index.js && cd -`

1. Create `src/components/Loading/index.js` 
  - **bash (from the root of the project):** `mkdir -p src/components/Loading && cd $_ && touch index.js && cd -`

1. Copy contents of pre-defined [Login Component](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/src/components/Login/index.js)

1. Copy contents of pre-defined [Loading Component](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/src/components/Loading/index.js)

## Add Login Validation and Functionality on StartScreen

[Reference: src/components/StartScreen/index.js](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/src/components/StartScreen/index.js)

1. Import Login component in StartScreen and replace _hello from react_ div

1. Establish two functions: `_handleFieldChange` and `_handleLogin`

1. Establish `componentDidMount` and `componentDidUpdate` functions and add this line to each: `componentHandler.upgradeDom();`

1. Add a constructor for `src/components/StartScreen/index.js` which creates a state for StartScreen and also properly bind the `_handleFieldChange` and `_handleLogin` functions

  ```javascript
  constructor(props) {
      super(props);

      this.state = {
        status: 'initial',
        email: '',
        password: ''
      };

      this._handleFieldChange = this._handleFieldChange.bind(this);
      this._handleLogin = this._handleLogin.bind(this);
  }
  ```
  
1. Pass required attributes to `<Login />`
  ```javascript
    <Login loading={this.state.loading} 
           email={this.state.email} 
           password={this.state.password} 
           handleFieldChange={this._handleFieldChange}  
           handleLogin={this._handleLogin}/>
  ```

1. Add `_showSnackBar` function
  ```javascript
    _showSnackBar(message) {
    var data = {
      message: message,
      timeout: 2500
    };
    var snackbarContainer = document.querySelector('#login-snack-bar');
    snackbarContainer.MaterialSnackbar.showSnackbar(data);
  }
  ```

1. Add email/password check in `_handleLogin`.  Invoke `UserService.login` if it passes validation.

1. Set app state to display loading during login process

1. Add stringify'd `USER_PROFILE` to localStorage on success, or invoke `_showSnackBar` on login error (incorrect email or pw)

1. Log parsed `USER_PROFILE` to console to demonstrate API response payload

## Navigate to Dashboard

1. While still in `src/components/StartScreen/index.js`, add this line of code to the top: `import {hashHistory} from 'react-router';`

1. On a successful login in the `_handleLogin` function, add `hashHistory.push('/dashboard');`

1. TEST: Navigate back to Login and Forward to Dashboard - `delete localStorage['USER_PROFILE']` - can no longer nav forward

## Add SCSS

1. Create `src/assets/styles/main.scss` 
  - **bash (from the root of the project):** `mkdir -p src/assets/styles && cd $_ && touch main.scss && cd -`

1. Uncomment Stylesheets require in `src/dependencies.js`

1. Copy contents of pre-defined [main.scss](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/src/assets/styles/main.scss)

## Give Dashboard some style

1. Create `src/assets/style/dashboard.scss`

1. Copy contents of pre-defined [dashboard.scss](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/src/assets/styles/dashboard.scss)

1. @Import `./dashboard.scss` in `src/assets/styles/main.scss`

1. Copy contents of pre-defined [`Dashboard/index.js`](https://raw.githubusercontent.com/ericnograles/rehacked-spa-basics/master/src/components/Dashboard/index.js)

## Dev Tools

1. Add [React Dev Tools Chrome Extension](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi) 

1. Under React tab - find StartScreen component and demonstrate setting state _loading = true_

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
