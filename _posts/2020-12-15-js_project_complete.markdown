---
layout: post
title:      "JS project complete!"
date:       2020-12-15 13:53:19 -0500
permalink:  js_project_complete
---


This project put me so far out of my comfort zone and while it was a bit intimidating, it felt extremely rewarding to figure out the pieces that weren't working. My biggest headache in the project was trying to figure out how to involve nested classes and display them correctly in JS. I was able to make an attachment on my form that corresponded with the foreign_key ID I wanted to associate the new object with, but it would come back with errors when trying to render. Fortunately, and after many hours of brainstorming why this was happening, I managed to figure out I had not added Include: :location to my create object. So when it created the object, it didn't have a location I could "${this.pet.location.name}" off of.  So adding that to the controller create action finally enabled me to view the newly created object correctly without needing to refresh the page! 

Another issue I had trouble with were promises: how they worked and when I needed to use them. In my project, I primarily used promises when calling and in my ApiService class where I was making requests to the API. Promises are important here because getting information, pushing requests and creating data is *not* instaneous. It takes time. Sometimes fractions of a second and sometimes several seconds depending on the extent of data being created or gathered. It's not very efficient or user friendly to stall your program to wait for these requests. Especially if there's other things you could be working on in the mean time. That's against the idea that your program should be Asynchronous, or always be working on a task while waiting for results from requests to return. 

So, again, what are Promises? Promises have 3 states. Pending, resolved and rejected. A promise is made to return data. In my project, I use a promise to gather data from the API. It would be meaningless if I tried to use data that wasn't there. Therefore it's important that I use the .then method which won't attempt to act on the data until it has been resolved. The biggest example of how my code runs asynchronously is on my index.js page! 


```
const api = new ApiService("http://localhost:3000/api/v1");

document.addEventListener("DOMContentLoaded", () => {
  
  Pet.getAll();
  Location.getAll();
  new PetForm();
  new LocationForm();
  
 

});
```

What is my index.js page doing? It's calling on a class method on each class. My program would run slower if it had to wait for my Pet.getAll get request to resolve before even looking at Location, PetForm and LocationForm. Now doing all of those things one a at a time seem really unintuitive. Not to mention a really slow experience for a user. 

