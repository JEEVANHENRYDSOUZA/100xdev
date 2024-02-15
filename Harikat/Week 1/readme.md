## Week 1
### Why languages
- Ram when we run a program it runs here
    - In ram only we get 1010101
    - Compiler converts it to 101010 language 
- Everything else is present in the memory 
### Commonly used JS API'S
- String 
    - str.length - gives current length of the string
    - str.indexOf - gives the index at what point the smaller string is present first appeareance
    - str.lastindexof - gives the last index of the string 
    - str.Slice(strt,end) - gives a part of string from start end , does not include last index
    - str.replace(target,replacement) - replaces the target with the replacement, if target not present same string is returned
    - str.split - an array is generated which is split  , splits string based on a delimitor
    - str.trim - removing spaces from start /  end
    - str.uppercase - uppercase
    - str.lowercase - lowercase
- Numbers
    - parseInt - this is global function , parsing a number to integer, if number contains string output is NaN
- Float
    - parseFloat - this is global function , parsing a number to float
- Array 
    - array.push - element  will be added at end 
    - array.pop - element  will be removed from end
    - array.shift - element will be removed from start 
    - array.unshift - element will be added at start 
    - array.concat(array2) - megre two arrays 
    - forEach(function(element of the array )) - will run for each element on the array 
    - array.map  
- Global Date Class : create a date object first 
    - currentDate.getDate()
    - currentDate.getMonth() + 1; // Months are zero-indexed, so adding 1
    - currentDate.getFullYear()
    - currentDate.getHours()
    - currentDate.getMinutes()
    - currentDate.getSeconds()
- JSON Data
    - JSON.parse(jsonString) - Parsing JSON string to JavaScript object
    - JSON.stringify(parsedObject) - Stringifying JavaScript object to JSON string
- Math 
    - Math.round(value)
    - Math.ceil(value)
    - Math.floor(value)
    - Math.random()
    - Math.max(5, 10, 15)
    - Math.min(5, 10, 15)
    - Math.pow(value, 2)
    - Math.sqrt(value)
- Objects
    - Object.keys(obj) - array of keys as string
    -  Object.values(obj) - array of objects as string
    - Object.entries(obj) - array of array of key and value
    - obj.hasOwnProperty("property")- returns a boolean  direct property of that object (not inherited through the prototype chain)
    - Object.assign({}, obj, { newProperty: "newValue" }) - first argument target object , second argument and third argumnet copied in to the first 
### Compiler vs Intepreted
- Compiler convert the high level language to low level language
- Compiled languages will compile entire file and then will run 
- If there is any error during the compilation stage compiled languages will not work 
- Interpreted language will run the file line by line
- They work even if there is a partial error in the code 
- JS is an interpreted language
### Why JS is better 
- Browser can understand JS without any hesitaion 
- Other languages can also be used but we need to use some third party libraries
- Thanks to nodejs as it is javascript
- It is dynamically typed language
### Single Threaded Nature Of JavaScript
- JavaScipt can only use one core at a time hence it is single threaded
- However we can split use some method to split the code on multiple core
### Map , filter , arrow functiosns 
- Map 
    - Syntax - array.map(num => num * num) , num is the individual elements passed in the array
        - Callback returns a value then that returned value will be the new element in the array
        - If Callback does not return any value then the new value in the array will be undefined
- Filter
    - Syntax - array.filter( function (num) { return num % 2 === 0 } )
        - The filter() method expects the callback function to return a boolean value indicating whether an element should be      included in the resulting array
        - If the callback returns true, the element is included; if it returns false, the element is excluded
### Async Functions
- Context Swtiching 
- They can do other tasks
- Parallilsm can be acheieved
- Delegating task to another worker
- Remember JavaScript is still single threaded 
- Some inbuilt Asyb functions are : 
    -  fs.readfile , Fetch , setTimeout 
### Sync Function 
- Can perform only function at a time
### Promises
- Before promise callback calls the function.Results are put in the callback queue. Goes to event loop. When stack is empty put on call stack
- This code is ugly and Promises makes the code look pretty way
- Promises are same as callback only thing , is promises overcome the drawback of callbacks
- The drawback of using callback, we cant rely on them due to callback hell 
- Also callback make the code base look ugly
- Solution we use Promise
- As the name suggest promise will always make sure that the underlying work is completed
- Syntax 
    - Return Promise object takes in a function that has two parameters reject and resolve
    - This resolve()
    - Whatever is in the resolve function is then given to the function mentioned in the .then method
    - Intially a Promise will always be in the pending stage
    - Later on they will be either 
### Using Async &  Await
- Still uses promises/callback under the hood 
- Asyn function return a promise
- Await will will until the promise is resolved/
- Await cannot be used at top level
- Await and async need to work together

