---
layout: post
title:      "JS project complete!"
date:       2020-12-15 18:53:19 +0000
permalink:  js_project_complete
---


This project put me so far out of my comfort zone and while it was a bit intimidating, it felt extremely rewarding to figure out the pieces that weren't working. My biggest headache in the project was trying to figure out how to involve nested classes and display them correctly in JS. I was able to make an attachment on my form that corresponded with the foreign_key ID I wanted to associate the new object with, but it would come back with errors when trying to render. Fortunately, and after many hours of brainstorming why this was happening, I managed to figure out I had not added Include: :location to my create object. So when it created the object, it didn't have a location I could "${this.pet.location.name}" off of.  So adding that to the controller create action finally enabled me to view the newly created object correctly without needing to refresh the page! So cool!
