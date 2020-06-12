---
layout: post
title:      "Hearthstone sort_by_flavor Method"
date:       2020-06-12 22:19:51 +0000
permalink:  hearthstone_sort_by_flavor_method
---


During my technical interview/API assessment I was tasked with changing my API to instead of sort alphabetically by name, sort alphabetically by the flavor text that the card has. The code I ended up writing was the following - 
```     
def self.sort_by_flavor
        self.all.sort { |a, b| a.flavor <=> b.flavor }
        # binding.pry
end
		``` 
		The reason I wanted to have the binding pry is to see exactly what was happening and to ensure that I had the arranging the correct data. The method works by selecting the array of [all] and sorting it by the syntax in the following hash, setting the key and value, |a,b|, and labeling "a and b as" .flavor to select what I was going to be sorting. 
		Having to research this on something not on an assignment was very insightful to me because it is very easy to use when asked, but to fully understand how to set the variables when freely coding had me stumped, and let me fully understand what I was doing when creating this. 
		
		To test that the code was working, I inserted it into my display_card_name method, which was originally written as - 
		```
		    def  display_card_name
        sleep(1)
        Mage.all.each.with_index(1) {|card, i| puts "#{i}. #{card.name}"}
        # binding.pry
    end
		```
		Once edited, it was written as -
		```
		    def  display_card_name
        sleep(1)
        Mage.sort_by_flavor.each.with_index(1) {|card, i| puts "#{i}. #{card.name}"}
        # binding.pry
    end
		```
		Which returned the array in the correct order. 


