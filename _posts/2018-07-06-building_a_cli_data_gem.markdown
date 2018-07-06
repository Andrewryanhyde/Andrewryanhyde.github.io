---
layout: post
title:      "Building a CLI Data Gem"
date:       2018-07-06 15:31:16 +0000
permalink:  building_a_cli_data_gem
---


For my latest project I decided to build a small command line interface app in Ruby called BookBuddy. BookBuddy allows a user to find the bestselling books and read some further information on the ones that catch their eye. 


I initially approached this project by noting the kind of attributes a book might have. Such as:

* Title 
* Author 
* Price
* Description 

I then set about building a book object that would allow me to store this data after we've scraped it from the retailers site using Nokogiri and Open URI 

The next step was to plan out the CLI in pseudo code that would assist me in knowing which functions/helpers to build and provide the general foundation for building out my application. 

My original approach was to build one general scraper method that would allow me to pull both the books general data (title, author, price etc) from the bestsellers list and build a second method that scraped the description from a link hidden in the index page's HTML. This seemed like a simple idea at the time but I later ran into issues when I struggled to pass the books URL value to a separate method. 

It soon became apparent that the most efficient way was to build two separate scraper methods, one for the index page to gain the book's title, author and price and another to scrape the description from the books individual page. With both methods feeding into an array of hashes that would then be iterated over to instantiate each book object. 

After putting together the scraper methods and choosing the css attributes to pull the right data it was just a matter of building out the remaining methods needed to turn our hashes of book data into new objects and building those into the CLI in order to display this new information to the user. 

On the first run the general structure seemed to be working well: 

![](https://preview.ibb.co/ikP8cJ/Screenshot_2018_07_06_at_11_44_33.png!)

But it seemed that although the information we were pulling was correct, we were also pulling in some extra whitespace which was causing those first few lines to appear blank. After a little investigation it appears that my CSS selectors weren't as accurate as they could have been and therefore it was pulling in some empty divs. After a quick edit the app was working brilliantly. 


**In Summary**

This was a great project to work on, I found it a little tricky at times but it's been great to put my learning into practice and has certainly cemented my knowledge in Object Oriented Ruby and web scraping. 

If you'd like to view the source code for this project it's available at https://github.com/Andrewryanhyde/BookBuddy






