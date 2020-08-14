---
layout: post
title:      "A rails api with a React/Redux frontend."
date:       2020-08-14 16:15:56 +0000
permalink:  a_rails_api_with_a_react_redux_frontend
---


React and redux really make building a website easy. By being able to compartmentalize the code you can track down the errors much faster and with greater ease. Regular JavaScript function like map and filter can be thrown in any component you create. This makes it supper easy to make the website interactive. The hardest challenges I found was how it all talked to each other but after doing a full build I was able to create more stuff efficiently. Knowing what the state and props are doing and when to call them is the most important part I found in react. Using Middleware, Connect and Thunk made this much easier. The code to make these work is extremely straight forward. 

import ReactDOM from 'react-dom';
import { Provider } from 'react-redux';
import { createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk'
import * as serviceWorker from './serviceWorker';

const store = createStore(rootReducer, composeWithDevTools(applyMiddleware(thunk)))

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);
serviceWorker.unregister();

Using a rails api backend made it very quick and easy to put things into props and then render onto the page.  A simple fetch request and I was on my way to giving usable content. 
export const getCards = () => {
    return dispatch => {
        dispatch({type: "LOADING_CARDS"})
        return fetch('/cards')
        .then(res => res.json())
        .then(cards => dispatch({type: "CARDS_LOADED", payload: cards}))
    }
}
I feel that react is a great way to make very interactive user friendly webpages in a short amount of time. Its always being updated with the latest features and I feel will only get easier to use over time.

