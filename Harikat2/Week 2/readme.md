## Documnent Object Model
### What is DOM 
- It is a progamming interface for web documents
- DOM is not a programming language
- It is a tree like structure 
- DOM represents documents as nodes and objects
- DOM was designed to be independent of language 
- It is a browser API 
- It is not a part of javascript language

### Selecting DOM elements
Selectors in the DOM (Document Object Model) are used to locate and manipulate HTML elements. In JavaScript, you can use various methods to select elements based on different criteria. Here are some common types of selectors:

1. **ID Selector (`getElementById`):**
   - Selects a single element by its unique ID attribute.
   ```javascript
   const element = document.getElementById('myElementId');
   // in case of multiple match we only get the first match
   ```
2. **Class Selector (`getElementsByClassName`, `querySelectorAll`):**
   - Selects elements based on their class attribute.
   ```javascript
   const elementsByClass = document.getElementsByClassName('myClassName');
   // in case of multiple match we get a list
   const elementsByClassQuery = document.querySelectorAll('.myClassName');
    const elementsByClassQuery = document.querySelector('.myClassName');
    //retruns the first occurance 
   ```
3. **Tag Name Selector (`getElementsByTagName`, `querySelectorAll`):**
   - Selects elements based on their HTML tag name.
   ```javascript
   const elementsByTag = document.getElementsByTagName('div');
   const elementsByTagQuery = document.querySelectorAll('div');
   ```
4. **Attribute Selector (`querySelectorAll`):**
   - Selects elements based on specific attributes.
   ```javascript
   const elementsByAttribute = document.querySelectorAll('[data-custom-attribute="value"]');
   ```
5. **Selector by Relationship (`querySelector`, `querySelectorAll`):**
   - Selects elements using CSS-style selectors, including descendant, child, adjacent sibling, and general sibling relationships.
   ```javascript
   const elementBySelector = document.querySelector('.parent .child');
   const elementsBySelector = document.querySelectorAll('.parent > .child');
   ``
6. **Query Selector (`querySelector`, `querySelectorAll`):**
   - Selects elements using CSS-style selectors, allowing for more complex queries.
   ```javascript
   const elementBySelector = document.querySelector('#myId .myClass');
   const elementsBySelector = document.querySelectorAll('div[data-custom="value"]');
   ```
7. **Nth Child Selector (`querySelectorAll`):**
   - Selects elements based on their position in a parent element.
   ```javascript
   const nthChildElements = document.querySelectorAll('.parentElement :nth-child(2)');
   ```

### NodeList vs Array 
`NodeList` and `Array` are both collections of elements in JavaScript, but they have some key differences in terms of their properties and available methods.

- NodeList:

1. **Dynamic:**
   - `NodeList` is often dynamic, meaning it is live and automatically updates when the DOM changes. If you select elements using `querySelectorAll`, the resulting `NodeList` will reflect changes in the DOM.

2. **Limited Methods:**
   - `NodeList` has a limited set of methods compared to arrays. It usually includes only a few methods like `item(index)` and `length`.

3. **No Array Methods:**
   - `NodeList` does not have the extensive set of array methods like `forEach`, `map`, `filter`, `reduce`, etc.

4. **Static Methods:**
   - Some DOM methods return a static `NodeList`, meaning it doesn't automatically update when the DOM changes. Examples include `getElementsByClassName` and `getElementsByTagName`.

5. **Index Access:**
   - Elements in a `NodeList` can be accessed by their index, like `nodeList[0]`.

- Array:

1. **Static:**
   - Arrays in JavaScript are typically static, meaning they don't automatically update when the underlying data changes.

2. **Extensive Methods:**
   - Arrays have a rich set of built-in methods for manipulation and iteration, such as `forEach`, `map`, `filter`, `reduce`, `indexOf`, `splice`, and many more.

3. **Non-live:**
   - Unlike `NodeList`, arrays don't automatically update when the underlying data changes. They are not live.

4. **Index Access:**
   - Elements in an array can be accessed by their index, like `array[0]`.

- Example:

```javascript
// NodeList
const nodeList = document.querySelectorAll('.example'); // Returns a NodeList
console.log(nodeList.length); // Accessing length property

// Array
const array = Array.from(nodeList); // Convert NodeList to Array
console.log(array.length); // Accessing length property
array.forEach(item => console.log(item)); // Using forEach method
```
### Creating new DOM elements
- Create a New Element: this will only create the element we will still have to add it to the DOM 
```javascript
const newDiv = document.createElement('div');
```

### Changing CSS properties
```javascript 
myElement.style.width = '300px';
myElement.style.height = '150px';
myElement.style.backgroundColor = 'lightgreen';
myElement.style.color = 'white'; // Changing text color
```
### InnerHtml vs TextContent
The primary difference between `innerHTML` and `textContent` lies in how they handle content within an HTML element:

1. **`innerHTML`:**
   - **Handles HTML Content:**
     - `innerHTML` is used to get or set the HTML content inside an element.
     - It allows you to work with HTML markup, and any HTML tags included in the content will be parsed and rendered.

     ```javascript
     const element = document.getElementById('myElement');
     element.innerHTML = '<strong>This is bold text</strong>';
     ```

   - **Security Considerations:**
     - While powerful, using `innerHTML` with user-provided data can pose security risks, as it may expose your application to cross-site scripting (XSS) attacks if the data is not properly sanitized.

2. **`textContent`:**
   - **Handles Plain Text Content:**
     - `textContent` is used to get or set the text content inside an element.
     - It treats everything as plain text, and any HTML tags included in the content will be treated as literal text and not rendered.

     ```javascript
     const element = document.getElementById('myElement');
     element.textContent = 'This is plain text';
     ```

   - **Security Considerations:**
     - `textContent` is safer when working with user input, as it avoids interpreting HTML tags, reducing the risk of XSS vulnerabilities.

### Using document.getElementbyId on a form 
1. **`form.elements`:**
   - The `form.elements` property returns a collection of all form controls (like input, select, textarea) within the form. It allows you to access individual form elements by their index or by their `name` attribute.

   ```javascript
   const form = document.getElementById('myForm');
   console.log('Form Elements:', form.elements);
   ```

2. **`form.action`:**
   - The `form.action` property returns the URL specified in the `action` attribute of the form. It represents the URL where the form data will be sent when the form is submitted.

   ```javascript
   const form = document.getElementById('myForm');
   console.log('Form Action:', form.action);
   ```
### Adding Elements to the DOM 

- Adding elements to the DOM (Document Object Model) involves creating new elements, configuring them, and appending or inserting them into the existing HTML structure. Here are several methods to achieve this using JavaScript:

### 1. **appendChild:**
   - Use `appendChild` to add a child element to a parent element. This method adds the specified node as the last child to the given parent node.

   ```javascript
   // Create a new div element
   const newDiv = document.createElement('div');
   newDiv.textContent = 'This is a new div!';

   // Get the parent element
   const parentElement = document.getElementById('parentContainer');

   // Append the new div to the parent element
   parentElement.appendChild(newDiv);
   ```

### 2. **insertBefore:**
   - Use `insertBefore` to insert a node before a specified existing child node. This method takes two arguments: the new node to insert and the reference node before which the new node should be inserted.

   ```javascript
   // Create a new div element
   const newDiv = document.createElement('div');
   newDiv.textContent = 'This is a new div!';

   // Get the parent element
   const parentElement = document.getElementById('parentContainer');

   // Get a reference to an existing child node
   const referenceNode = parentElement.firstChild;

   // Insert the new div before the reference node
   parentElement.insertBefore(newDiv, referenceNode);
   ```

### 3. **insertAdjacentHTML:**
   - Use `insertAdjacentHTML` to insert HTML at a specified position relative to the element. This method takes two arguments: the position ('beforebegin', 'afterbegin', 'beforeend', or 'afterend') and the HTML to insert.

   ```javascript
   // Get the target element
   const targetElement = document.getElementById('targetElement');

   // Insert HTML after the target element
   targetElement.insertAdjacentHTML('afterend', '<div>This is new content</div>');
   ```

### 4. **innerHTML:**
   - Use `innerHTML` to set the HTML content of an element. This can be useful when you want to replace the entire content of an element with new HTML.

   ```javascript
   // Get the target element
   const targetElement = document.getElementById('targetElement');

   // Set new HTML content
   targetElement.innerHTML = '<p>This is new content</p>';
   ```

### Removing Dom Elements
### 1. **removeChild:**
   - Use the `removeChild` method to remove a specific child node from its parent.

   ```javascript
   // Get the parent element
   const parentElement = document.getElementById('parentContainer');

   // Get the child element to remove
   const childToRemove = document.getElementById('childToRemove');

   // Remove the child element
   parentElement.removeChild(childToRemove);
   ```

### 2. **remove:**
   - Use the `remove` method, which is a more modern and concise way to remove an element. This method can be called directly on the element you want to remove.

   ```javascript
   // Get the element to remove
   const elementToRemove = document.getElementById('elementToRemove');

   // Remove the element
   elementToRemove.remove();
   ```

### 3. **replaceWith:**
   - Use the `replaceWith` method to replace an element with another one or with a set of nodes.

   ```javascript
   // Get the element to replace
   const elementToReplace = document.getElementById('elementToReplace');

   // Create a new element to replace it with
   const newElement = document.createElement('div');
   newElement.textContent = 'This is the replacement';

   // Replace the element
   elementToReplace.replaceWith(newElement);
   ```

### 4. **parentNode:**
   - Use the `parentNode` property to navigate to the parent node and then remove the child.

   ```javascript
   // Get the element to remove
   const elementToRemove = document.getElementById('elementToRemove');

   // Remove the element by accessing its parent node
   elementToRemove.parentNode.removeChild(elementToRemove);
   ```

### 5. **innerHTML:**
   - Use `innerHTML` to set the HTML content of a parent element, excluding the element you want to remove.

   ```javascript
   // Get the parent element
   const parentElement = document.getElementById('parentContainer');

   // Set innerHTML excluding the element to remove
   parentElement.innerHTML = parentElement.innerHTML.replace('<!-- elementToRemove -->', '');
   ```

### Traversing the DOM tree


### Common Properties:

1. **`nodeType`:**
   - Gets the type of the node. Common values include:
     - `1` for element nodes
     - `3` for text nodes
     - `8` for comment nodes
     - `9` for the document node

2. **`nodeName` and `localName`:**
   - `nodeName` gets the name of the node, including the namespace prefix.
   - `localName` gets the local part of the name, without the namespace prefix.

3. **`nodeValue`:**
   - Gets or sets the value of the node, depending on its type.

### Common Methods:

1. **`appendChild(newNode)`:**
   - Adds a new child node to the end of the list of children of the calling node.

2. **`removeChild(childNode)`:**
   - Removes a child node from the list of children of the calling node.

3. **`replaceChild(newNode, oldNode)`:**
   - Replaces one child node of the calling node with another.

4. **`cloneNode(deep)`:**
   - Creates a copy of the node. If `deep` is `true`, it also copies the node's descendants.

5. **`hasChildNodes()`:**
   - Returns a Boolean indicating whether the node has any child nodes.

6. **`parentNode`:**
   - Returns the parent node of the specified node.

7. **`nextSibling` and `previousSibling`:**
   - `nextSibling` returns the node immediately following the specified one.
   - `previousSibling` returns the node immediately preceding the specified one.

8. **`firstChild` and `lastChild`:**
   - `firstChild` returns the first child node of the specified node.
   - `lastChild` returns the last child node of the specified node.

9. **`textContent`:**
   - Gets or sets the text content of the node and its descendants.

10. **`querySelector` and `querySelectorAll`:**
    - `querySelector` returns the first element that matches a specified CSS selector.
    - `querySelectorAll` returns a NodeList of all elements that match a specified CSS selector.

11. **`setAttribute(name, value)`:**
    - Sets the value of an attribute on the specified element.

12. **`getAttribute(name)`:**
    - Gets the value of an attribute on the specified element.


### HTML Collection VS NodeList
Both `HTMLCollection` and `NodeList` are collection objects in JavaScript that represent a set of nodes in the Document Object Model (DOM). They are often used to store a list of elements that are retrieved from the DOM using various methods. However, there are some differences between them.

### HTMLCollection:

- **Live Collection:**
  - `HTMLCollection` is a live collection, meaning it's automatically updated when the underlying DOM changes. If elements are added or removed from the DOM, the `HTMLCollection` is updated accordingly.

- **Limited Methods:**
  - `HTMLCollection` has a limited set of methods compared to `NodeList`. Common methods include `item(index)` and `namedItem(name)`.

- **Specific to Element Properties:**
  - `HTMLCollection` is typically used to represent collections of elements with a specific property, like a collection of elements with a particular tag name or a collection of elements in a form.

- **Indexed Access:**
  - You can access elements in an `HTMLCollection` using index notation (e.g., `collection[0]`).

### NodeList:

- **Live or Static:**
  - `NodeList` can be either live or static. A live `NodeList` is updated when the DOM changes, similar to `HTMLCollection`. A static `NodeList` is a snapshot of the DOM at the time the `NodeList` is created.

- **More Methods:**
  - `NodeList` provides a broader set of methods compared to `HTMLCollection`. Common methods include `item(index)`, `forEach(callback)`, `keys()`, `values()`, `entries()`, etc.

- **Not Limited to Elements:**
  - `NodeList` is more versatile and can represent a collection of various node types, not just elements. It can include text nodes, comment nodes, etc.

- **Indexed or Named Access:**
  - You can access elements in a `NodeList` using index notation or named access (e.g., `collection[0]` or `collection.namedItem('name')`).

### When to Use Each:

- If you specifically need a live collection that automatically updates with DOM changes and you are dealing with a collection of elements with a specific property, `HTMLCollection` might be appropriate.

- If you need a more versatile collection that includes various node types and offers a broader range of methods, or if you want a static snapshot of the DOM, `NodeList` is often a better choice.

In many cases, the choice between `HTMLCollection` and `NodeList` depends on the specific requirements of your task or application. Keep in mind that modern browsers have become more consistent in their behavior, and in some cases, the practical differences between `HTMLCollection` and `NodeList` might be minimal
