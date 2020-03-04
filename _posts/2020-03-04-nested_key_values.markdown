---
layout: post
title:      "Nested Key Values"
date:       2020-03-04 09:25:08 +0000
permalink:  nested_key_values
---

Deriving key/value pairs from data is a useful task in Ruby. The basic method for this looks something like :

`def attributes_from_hash(event)
  event.each do |k, v|
   send("#{k}=", v)
	end`
 
 With a basic hash, we may get a response similar to:
 `"id": "EONET_4604",
   "title": "Wildfire - Codegua, Chile",`

However sometimes we may encounter key value pairs within other key value pairs, and have to perform a more comlplex iteration  after our first iteration, in order to extract these key values. Now we can execute this method without encountering errors!

` def attributes_from_hash(event)  
   event.each do |k, v|
    send("#{k}=", v)
   end
    **  event.each_with_object([]) do |(k,v), keys|
       keys << k 
        keys.concat(event_from_hash(v)) if v.is_a? Hash**
    end
  end `
		
	
	Now we can get the response we wanted!
	
	` "id": "EONET_4604",
      "title": "Wildfire - Codegua, Chile",
		"geometries":
         "date": "2020-03-02T15:44:00Z",
         "type": "Point",
         "coordinates": [
            -70.608937502,
            -34.304746971`
						
			*Here, "date/type/coordinates" are nested key/value pairs within "geometries"... which is a key within the "events" class
		
		
		
		
		
