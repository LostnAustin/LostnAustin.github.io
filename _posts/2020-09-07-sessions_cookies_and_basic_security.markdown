---
layout: post
title:      "Sessions, cookies, and basic security"
date:       2020-09-07 10:15:44 +0000
permalink:  sessions_cookies_and_basic_security
---


Sessions in Sinatra are an important and useful addition. Many websites have the ability to let users create accounts, in order to do things such as buy products, receive email alerts, etc. 

For websites that use a login system, sessions are used to create a system that allows two other systems to communicate while secured, such as a server and a client running the web page. Cookies are used to store this session data. Session cookies allow a website to keep track of your movement from page to page for that specific session. This will only be activewhile logged in, or until you close the browser.

Sessions are "enabled" within the controller, for instance:
```configure do 
    enable :sessions
		set :session_secret, "website_secret"
		end
		
		get '/index' do
		erb :'/index'
		end
		```
		
		
		These lines of code allow access to sessions and creates an encryption key using the "set:session_secret, "website_secret" that will by utilized in creating a session_id. Then we can write a method in the same controller to set our session to our user.
		``` def current_user
    @current_user |= User.find_by(id: session[:user_id])
  end ```
	
	From here you could create a page, say index.erb to go with our 'get' method, and add some Ruby code to the html such as
	```<% if current_user %>
	     <h1>Hello!</h1>
			 <% else %>
			 <h1>Please sign in or sign up!</h1>
			 <% end %>
			 ``` 
			 Now, if a user is within the database and signed in, they will see "Hello!" but if not signed in they will see "Please sign up or sign in!"
	*You should not define a session_secret in general as shown for this simplified example. It would be more appropriate to view the Sinatra documentation on using a secure number generator.
