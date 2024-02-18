## Event Propogation 
### Event Bubbling
Event bubbling is one of the phases of event propagation in the Document Object Model (DOM). In the bubbling phase, an event starts from the target element and bubbles up through its ancestors in the DOM hierarchy. Here's a simple example demonstrating event bubbling using HTML and JavaScript:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Event Bubbling Example</title>
  <style>
    div {
      padding: 20px;
      margin: 10px;
      border: 1px solid #ccc;
    }
  </style>
</head>
<body>

  <div id="outerDiv">
    Outer Div
    <div id="middleDiv">
      Middle Div
      <div id="innerDiv">
        Inner Div
      </div>
    </div>
  </div>

  <script>
    // Function to handle the click event
    function handleClick(event) {
      console.log(`Clicked on ${event.currentTarget.id}`);
    }

    // Attach click event listeners to each div
    const outerDiv = document.getElementById('outerDiv');
    const middleDiv = document.getElementById('middleDiv');
    const innerDiv = document.getElementById('innerDiv');

    outerDiv.addEventListener('click', handleClick);
    middleDiv.addEventListener('click', handleClick);
    innerDiv.addEventListener('click', handleClick);
  </script>

</body>
</html>
```

In this example:

- There are three nested `<div>` elements: `outerDiv`, `middleDiv`, and `innerDiv`.
- Each `<div>` has a click event listener attached to it using the `addEventListener` method.
- When you click on the `innerDiv`, the event bubbles up through the ancestor elements (`middleDiv` and `outerDiv`), triggering the click event listeners on each ancestor.

```
Clicked on innerDiv
Clicked on middleDiv
Clicked on outerDiv
```


### Event Capturing
Event capturing is one of the two phases of event propagation in the Document Object Model (DOM). The event propagation process involves the capturing phase and the bubbling phase. Here's an overview of event capturing:

1. **Event Flow:**
   - Event capturing is the first phase in the event flow process.
   - During the capturing phase, the event travels from the outermost ancestor (the root of the DOM tree) down to the target element where the event originated.

2. **`addEventListener` with `capture` Option:**
   - You can specify the use of the capturing phase when attaching an event listener using the `addEventListener` method.
   - The third parameter is an options object, and you can set the `capture` property to `true` to indicate that the event listener should be executed during the capturing phase.

   ```javascript
   element.addEventListener('click', handleClick, true);
   ```

   In this example, the `handleClick` function will be called during the capturing phase when a click event occurs on the specified `element`.

3. **Order of Execution:**
   - During the capturing phase, event listeners are executed in the order of the DOM hierarchy from the outermost ancestor down to the target element.
   - If multiple elements are nested, the capturing phase starts from the outermost ancestor and moves down through each level of the hierarchy.

4. **Stopping Propagation:**
   - Inside an event listener during the capturing phase, you can use `event.stopPropagation()` to stop the event from further propagating. This prevents the event from reaching the target element and entering the bubbling phase.

   ```javascript
   function handleClick(event) {
     // Stop further propagation during capturing
     event.stopPropagation();
     // Your event handling code here
   }
   ```

   Keep in mind that using `event.stopPropagation()` in the capturing phase prevents the event from reaching the target element.

### Default Method
- By defualt we follow event bubbling

### Different types of Event
Events in web development are interactions or occurrences that happen in the browser. These events can be triggered by the user, the browser, or the web page itself. Here are some common types of events in web development:

1. **Mouse Events:**
   - **click:** Occurs when the mouse is clicked.
   - **dblclick:** Occurs when the mouse is double-clicked.
   - **mousedown:** Occurs when a mouse button is pressed down.
   - **mouseup:** Occurs when a mouse button is released.
   - **mousemove:** Occurs when the mouse pointer is moved.
   - **mouseover:** Occurs when the mouse pointer enters an element.
   - **mouseout:** Occurs when the mouse pointer leaves an element.

2. **Keyboard Events:**
   - **keydown:** Occurs when a key is pressed down.
   - **keyup:** Occurs when a key is released.
   - **keypress:** Occurs when a key is pressed and released.

3. **Form Events:**
   - **submit:** Occurs when a form is submitted.
   - **reset:** Occurs when a form is reset.
   - **change:** Occurs when the value of an input element changes.
   - **input:** Occurs when the value of an input element is being changed.

4. **Focus Events:**
   - **focus:** Occurs when an element receives focus.
   - **blur:** Occurs when an element loses focus.

5. **Window Events:**
   - **load:** Occurs when a web page or an image has finished loading.
   - **unload:** Occurs when the user navigates away from a page.
   - **resize:** Occurs when the browser window is resized.
   - **scroll:** Occurs when the user scrolls the page.

6. **Document Events:**
   - **DOMContentLoaded:** Occurs when the HTML document has been completely loaded and parsed.
   - **readystatechange:** Occurs when the readyState of the document changes.
   - **DOMContentLoaded:** Occurs when the DOM is fully loaded, including stylesheets and images.

7. **Media Events:**
   - **play:** Occurs when media playback starts.
   - **pause:** Occurs when media playback is paused.
   - **ended:** Occurs when media playback completes.

8. **Touch Events:**
   - **touchstart:** Occurs when a touch point is placed on the touch surface.
   - **touchmove:** Occurs when a touch point is moved along the touch surface.
   - **touchend:** Occurs when a touch point is removed from the touch surface.

9. **Drag and Drop Events:**
   - **dragstart:** Occurs when an element starts being dragged.
   - **drag:** Occurs when an element is being dragged.
   - **dragend:** Occurs when the drag operation is completed.

These events can be handled using JavaScript by attaching event listeners to specific elements. Event listeners are functions that get executed in response to a particular event. For example:

```javascript
document.getElementById('myButton').addEventListener('click', function() {
  console.log('Button clicked!');
});
```


