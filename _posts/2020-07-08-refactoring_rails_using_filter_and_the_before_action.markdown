---
layout: post
title:      "Refactoring Rails using Filter and the before action."
date:       2020-07-08 15:16:04 -0400
permalink:  refactoring_rails_using_filter_and_the_before_action
---


Rails has many built in methods that can assist making it much easier to get up and running. There are quite a few filters and validations that can be applied to make it dryer and not repetitive with code. You can apply filters before, around and after in controllers but one commonly used is the before_action to check if the a user is logged in etc.
The before_action filter is run before any methods are run in the controller. Filters on the application controller will inherit to all controllers but if the before_action filter is used on any other controller it will only be applied to just that controller. 

The :only option is used to make it only available to the methods and routes listed. It will only run when a user goes to the routes that are included in the only portion.
before_action :current_list, only: [:new, :create]
    	before_action :current_item,  only: [:show, :destroy]

You then make the method private so that it can’t be seen or altered. To clean up my code I made a private method like so.
 
    private 
    def current_list
        @list = current_user.lists.find_by_id(params[:list_id])
    end

    def current_item
        @item = Item.find_by(id: params[:id])
    End
		
This will keep the code from being accessed and the code will not be able to be used to try and hack the site while making the code more dynamic. To use the callback all I have to do is call   current_item or current_list in whatever method I need it.

Now my code is much dryer and not repetitive but still accomplishes the same goal. If I added more to the site and needed the same code, I could just add the method to the ‘only’ part of the filter and call on the private method making it cleaner and faster to create more content.

Rails provides lots of methods and filters using the ruby language making it mush faster and easier to publish working sites and keep the code easy to read. The more I use rails the easier it gets but I found it to be a little overwhelming at first with all the built-in things it can do. I am always finding new ways to do things that also make it cleaner.

