# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.
- Use at least 5 different HTML elements.
- Ensure semantic correctness.

Happy Coding! 💻✨


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>DOM Manipulation Example</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <h1 id="main-title">Original Title</h1>
  <p id="text-paragraph">This is some text.</p>

  <button id="change-text-btn">Change Text</button>
  <button id="change-style-btn">Change Style</button>
  <button id="toggle-element-btn">Add/Remove Element</button>

  <div id="container"></div>

  <script src="script.js"></script>
</body>
</html>

document.getElementById('change-text-btn').addEventListener('click', () => {
  const paragraph = document.getElementById('text-paragraph');
  paragraph.textContent = "The text has been changed dynamically!";
});

// Modify CSS styles via JavaScript
document.getElementById('change-style-btn').addEventListener('click', () => {
  const title = document.getElementById('main-title');
  title.style.color = 'tomato';
  title.style.backgroundColor = '#f0f0f0';
  title.style.padding = '10px';
  title.style.borderRadius = '5px';
});

// Add or remove an element when a button is clicked
const container = document.getElementById('container');
let elementAdded = false;

document.getElementById('toggle-element-btn').addEventListener('click', () => {
  if (!elementAdded) {
    const newElement = document.createElement('div');
    newElement.id = 'dynamic-element';
    newElement.textContent = 'I am a new element!';
    newElement.style.marginTop = '10px';
    newElement.style.padding = '10px';
    newElement.style.backgroundColor = 'lightblue';
    container.appendChild(newElement);
    elementAdded = true;
  } else {
    const existingElement = document.getElementById('dynamic-element');
    if (existingElement) {
      container.removeChild(existingElement);
    }
    elementAdded = false;
