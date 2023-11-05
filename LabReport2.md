# Lab Report 2

In this lab we created a Java program called StringServer which adds strings to a list and outputs the strings.

## StringServer Code

![Image](StringServer.png)

## Using AddMessage 

![Image](AddMessage1.png)

The method that gets called is handleRequest(); 

It takes the url as an URI variable which is set to the name url. At the time of this, the ArrayList strings is empty.

After running through the code it checks to see if /add-message is in the url, if it is it takes everything after the query ?s= and puts that string into the ArrayList strings. It then creates a StringBuilder, named list, goes through all of the strings in the ArrayList strings, adds them to the StringBuilder along with being numbered, and then returns it as a string.

The only fields that was permanetly changed was the ArrayList strings which now holds the string, "Hello". The StringBuilder list was also created and changed, but it is recreated everytime a new message is added so it won't impact future usage. 

## Using AddMessage Again

![Image](AddMessage2.png)

The method that gets called is handleRequest(); 

It takes the url as an URI variable which is set to the name url. At the time of this, the ArrayList strings holds the string, "Hello".

After running through the code it checks to see if /add-message is in the url, if it is it takes everything after the query ?s= and puts that string into the ArrayList strings. It then creates a StringBuilder, named list, goes through all of the strings in the ArrayList strings, adds them to the StringBuilder along with being numbered, and then returns it as a string.

The only field that was permanently changed was the ArrayList strings which now holds the strings, "Hello" and "How are you". The StringBuilder list was also created and changed, but it is recreated everytime a new message is added so it won't impact future usage. 

## Path's To Keys

![Image](PrivateKey1.png)

This is the private ssh key that is on my computer under /Users/slatermutunga/.ssh/id_rsa

![Image](PublicKey1.png)

This is the public ssh key that is in my ieng6 account under /home/linux/ieng6/cs15lfa23/cs15lfa23es/.ssh/authorized_keys

![Image](LogIn.png)

This is me logging in without inputting a password.

## What I learned in Weeks 2 and 3

Since I am currently in CSE30 where we are using ssh, and scp, frequenetly that was not new information for me. However this was my first experience with hosting a server. It was really cool to me how easy it was and how you could change it through the URL. Knowing how to do the simple StringSearch has me confident to tackle other website types. I am starting to understand how websites work, and now look at thinks like URL's much differently.





