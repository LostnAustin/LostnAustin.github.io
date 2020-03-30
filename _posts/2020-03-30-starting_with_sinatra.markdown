---
layout: post
title:      "Starting with Sinatra"
date:       2020-03-30 07:09:14 +0000
permalink:  starting_with_sinatra
---


Sinatra works as a bare bones framework for Model-View-Control (MVC) work. 

From within your project, in terminal run bundle init. We will refer to ours as App.rb.
Enter the 'config.ru' file

Here we will add 
``require 'sinatra'
require_relative './app.rb'
run App
``

Now we can go back to the main .rb file (app.rb in this case) and write:
``class App < Sinatra::Base
get '/' do
"Hello, World!"

end
end``

Our "App" class inherits from the SInatra base.

Now if you run "Rackup" from the terminal, you should be able to view your file (using httpserver and/or Shotgun).



