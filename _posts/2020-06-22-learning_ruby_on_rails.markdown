---
layout: post
title:      "Learning Ruby on Rails"
date:       2020-06-22 18:46:44 +0000
permalink:  learning_ruby_on_rails
---


I found this subject to be quite hard. It’s great that you can accomplish so much with very little code but the number of things it can do is a bit overwhelming. I found it hard to know when to use certain helpers and when I needed custom methods. I found methods like the before_action to be very helpful. 
before_action :require_permission, only: :show 

    def require_permission
        if current_user != List.find(params[:id]).user
            redirect_to lists_path
        end
        rescue ActiveRecord::RecordNotFound
        redirect_to root_url, :flash => { :error => "Record not found." }
    end
		
This project made me really dial in my troubleshooting skills as things did not seem to work the way I 
Was expecting. I relied on Pry very heavily to find what the params and other values were to make my decision on what to use and where. 
		
I also learned a lot about ruby server as to how it is not compatible with certain browser plugins and add blockers and would just not update without a restart. 

This project made the Ruby and Sinatra project seem really small. The indepth nature of this project gave me a much greater understanding of why the fundamentals of object, classes, and different variables are essential. My understanding of all the parts that go into relationships is now well defined and I feel I will have a much greater understanding of how larger project will work in the future. 

