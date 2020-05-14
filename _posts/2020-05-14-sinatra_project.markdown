---
layout: post
title:      "Sinatra Project"
date:       2020-05-14 15:01:12 +0000
permalink:  sinatra_project
---


I found this project to be great fun but did run into a few hurdles. First the defaults that Cornial created caused me issues and broke pry so I was stuck using just the errors in the browser and a rake counsel. 
The default config.ru file also caused me issues with my edit pages giving a 500 error. After commenting this line out it all worked. 
# if ActiveRecord::Migrator.needs_migration?
#   raise 'Migrations are pending. Run `rake db:migrate` to resolve the issue.'
# end
I had struggled in the past with using gsub expressions but feel I learned a great deal writing this one. This one goes through a block of text and grabs any image URL’s and adds an image source tag on it so it will render in the browser. 
regexp = /(\S+\.(jpg|gif|png)(\/\S+)?(.*))/
@description = @route.description.gsub(regexp) { |url| "<img src='#{url}' height='75%' width='75%'>" } 
I really learned how all the aspects of what I had been studding do and how to adapt them into a working environment. It was also really exciting to see with Sinatra and Active Record how much functionality you can get with very little code.
I decided to do something with my project that I would actually use. I will be publishing it in a live environment and using it to log stuff for myself so it feels even more satisfying to make it work well.

