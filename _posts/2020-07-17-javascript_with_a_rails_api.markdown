---
layout: post
title:      "JavaScript with a Rails API"
date:       2020-07-17 17:56:57 +0000
permalink:  javascript_with_a_rails_api
---


Building a Rails API was really easy and quick by using the rails new and scaffolding commands. Creating functionality this way was made very simple and efficient. Serializers also make it really easy to add more components to the site for quick development. Even using JavaScript for the front end you can still watch the server update with sql code allowing you to know if its doing what you want it to do.

I love that using JavaScript for a frontend makes it so there is no page refreshes and the site feels very interactive. The new ES6 syntax is really nice to code with and cuts down on a lot of typing with arrow functions. Also having variables that aren’t hoisted make for a lot more control. JavaScript does a good job with working with json but was a bit of a learning curve. Using fetch and .then to update or get the json was a bit confusing at first but felt more natural after working with it for a while. 

fetch(BASE_URL+"/pcs")
    .then(resp => resp.json())
    .then(pcs => {
        pcs.forEach(pc => {
            let pd = new Pd(pc)
            showPcs.innerHTML += pd.renderPc()
            pd.renderULs()
        })
This code was used to fetch all the pc items and display them. 
The development tools in chrome are amazing with JavaScript and allow you to see all the variables and json properties. You can add break point or just step through the code one line at a time to see what is changing or happening. 

