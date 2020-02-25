---
layout: post
title:      "Object Labs"
date:       2020-02-25 08:31:58 +0000
permalink:  object_labs
---


The main take away for me from this section is utilizing attributes of an object class by using the "attr_accessor" to make attributes available throughout the different class methods you may be building.  Attr_accessors represent instances of the defined attribute. For instance, if we create the proper attr_accessor's and then define our initialize method utilizing the instance variables (@'s) we can access instance values. In the case of this initialize method, we are accessing those instances upon the initialization of a cash register instance, and setting those variable equal to the desired values.

``class CashRegister
  attr_accessor :total, :last_price, :discount, :quantity, :title, :price

  def initialize(discount = 0 )
    @total = 0
    @discount = discount
    @items = []
    @last_price = []
  end
	``
	
	The ability to access instances of information is a key component of using Ruby objects and classes.
