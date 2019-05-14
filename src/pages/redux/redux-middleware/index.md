---
title: Redux Middleware
---
## Redux Middleware

<!-- The article goes here, in GitHub-flavored Markdown. Feel free to add YouTube videos, images, and CodePen/JSBin embeds  -->
#### Middleware

Simply put middleware is a software component which provides services to integrate disparate system together(Wikipedia). Middleware can also be functions that have access to the request object (req), the response object (res), and the next function in the application's request-response cycle as stated on Expressjs. See the screenshot below:

![alt text](https://cdn-images-1.medium.com/max/1200/1*irFGoe-dbRHSzcA6zIM8PA.png)

#### Redux Middleware
Redux middleware is a snippet of code that provides a third-party extension point between dispatching an action and the moment it reaches the reducers.
See this

![alt text](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTOfFFnxcX8jCmppW45hewXoltIxtpWy3c6QrdXYnaUY7wLWrU5_g)
Note: All these happen within the store( the redux single source of truth). Every middleware has next() that calls the next action in the line.

It is a way to extend redux with custom functionality. They let you wrap the store's dispatch method for fun and profit. There are a number of them available for you. They include redux-logger, redux-thunk, redux-promise etc. The redux-thunk extends the functionality of a normal redux action to return a function instead of an object of the new state. Redux-logger extends redux native functionality by introducing a logger to log actions when dispatching them before reducers reduce the state. See the screenshot below:

![Redux thunk analogy](https://cdn-images-1.medium.com/max/1600/1*vtYeZg_wvFsm6aKpi70_Og.png)

#### ApplyMiddleware
This is a function packaged with redux that accepts one or more middlewares and returns a function. It is a store enhancer usually place after every other store enhancer you may use. The screenshot below shows how the applyMiddleware can be used to apply a number middleware to the store dispatch function.

Example

```
import { createStore, applyMiddleware } from 'redux'
import rootReducer from './reducers'
import reduxLogger from 'redux-logger'
import reduxThunk from 'redux-thunk'

const store = createStore(rootReducer, applyMiddleware(reduxLogger, reduxThunk))
```

#### More Information:
<!-- Please add any articles you think might be helpful to read before writing the article -->
- [Redux Middleware](https://redux.js.org/advanced/middleware)
- [Apply Middleware](https://redux.js.org/api/applymiddleware#applymiddlewaremiddleware)


