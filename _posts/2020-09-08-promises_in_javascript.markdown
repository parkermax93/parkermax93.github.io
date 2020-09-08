---
layout: post
title:      "Promises in JavaScript"
date:       2020-09-08 20:35:46 +0000
permalink:  promises_in_javascript
---


**Promises** - "A Promise is an object representing the eventual completion or failure of an asynchronous operation. Essentially, a promise is a returned object you attach callbacks to, instead of passing callbacks into a function."

**What do promises do?**
As shown in the definition of the promise, it returns an object that you attach callbacks to, instead of passing callbacks into a function. When creating a promise, there are esentially 4 states, fulfilled, which is an action relating to the promise succeeding, rejected, which is an action relating to the promise failing, pending, which is awaiting a promise response because it has not yet been fulfilled or rejected, and lastly, settled, where a promise has been either fulfilled or rejected. 

**Why are promises important for JavaScript?**
Promises are the ideal choice for handling asynchronous operations in the simplest manner. They can handle multiple asynchronous operations easily and provide better error handling than callbacks and events. Without promises, events and functions would need to be used but they have limited functionalities and would lead to having unmanageable code.

**When do you need a promise?**
You need a promise to interact with a .then response, which is an asynchronous answer to a recieved promise object. In the example of a fetch request, a promise is a received response object from the server that you .then convert into a json format if the promise returns resolved.

```
    getCharacters() {
        fetch(this.baseUrl).then(response => response.json()).then(json => createCharacters(json.data))
    }
```
In this snip of code from my project, the promise is in the fetch(this.baseUrl), and once that promise returns "fulfilled", then (.then) the (response) is converted to json(), and finally (.then), the json is used as the data that is taken in by the createCharacters function diving further into my code with the data.
