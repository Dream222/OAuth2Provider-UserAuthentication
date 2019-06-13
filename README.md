# Authentication Provider for the Social Accounts V1
User authentication in SPA, built with Node.js and React (Koa, Passport, Redux, Redux-Saga, React Router). Local authentication, where users can log in using a username and passport and authentication through Facebook.

[Authenticating Users in SPA using Node, Passport, React and Redux](http://andrejgajdos.com/authenticating-users-in-single-page-applications-using-node-passport-react-and-redux/)

## Preview

<img src="https://raw.githubusercontent.com/AndrejGajdos/auth-flow-spa-node-react/master/media/auth-flow-in-spa-preview.gif" width="500">


## Configuration

If you want to use authentication with facebook, you need to create a new [facebook app](https://developers.facebook.com/docs/apps/register/), enable OAuth Login in `Settings -> Facebook Login` and add `Valid OAuth Redirect URIs`. Then you need to copy `Client Token` and `App Id` into [.env](https://www.npmjs.com/package/dotenv) file in root of project folder.

## Install and Run

1) Install [Redis](https://redis.io/topics/quickstart)

2) Install npm dependencies

```bash
# install dependencies
$ npm i
```

```bash
# run project

# run redis
$ redis-server

# run webpack server to serve front-end code
$ npm run webpack

# run node.js server
$ npm run api
```


## issues
```
ERROR in ./index.jsx
Module build failed: SyntaxError: Unexpected token (23:4)

  21 | const store = createStore(
  22 |   combineReducers({
> 23 |     ...reducers,
     |     ^
  24 |     router: routerReducer,
  25 |   }),
  26 |   composeWithDevTools(applyMiddleware(routerMiddleware(history), sagaMiddleware)),

 @ multi babel-polyfill ./index.jsx
ℹ ｢wdm｣: Failed to compile.

```
***
```
You can simply install the Babel "Object rest spread transform" preset like so: 
npm install --save-dev babel-plugin-transform-object-rest-spread

And add it to your list of plugins:

{
    "plugins": [
        // Other plugins...
        "transform-object-rest-spread"
    ]
}
```