Here’s a comprehensive table summarizing the methods and properties learned across the sections on selecting, traversing, and manipulating DOM elements. The table includes detailed examples, descriptions, return types where necessary, and additional columns for Do’s and Don’ts.

### **DOM Methods and Properties Table**

| **Feature**               | **Description**                                                                 | **Example**                                                                                                 | **Return Type**              | **Do’s**                                                                                     | **Don’ts**                                                                       | **Gotchas**                                                                                       |
|---------------------------|---------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|------------------------------|---------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **`getElementById()`**    | Selects an element by its ID.                                                     | `document.getElementById('myId')`                                                                         | `HTMLElement`                | Use for unique element IDs.                                                                 | Avoid using IDs that may be duplicated.                                           | Only returns the first matching element; IDs should be unique.                                |
| **`getElementsByName()`** | Selects elements by their name attribute.                                         | `document.getElementsByName('myName')`                                                                    | `NodeList`                   | Useful for form elements.                                                                    | Name attributes can be duplicated, so ensure the right element is targeted.      | NodeList is not live; use `querySelectorAll` for a static collection.                          |
| **`getElementsByTagName()`** | Selects elements by their tag name.                                                | `document.getElementsByTagName('div')`                                                                    | `HTMLCollection`             | Good for selecting all elements of a specific type.                                         | Tag names are case-sensitive in XML; ensure proper casing.                       | HTMLCollection is live; updates automatically.                                                 |
| **`getElementsByClassName()`** | Selects elements by their class names.                                              | `document.getElementsByClassName('myClass')`                                                              | `HTMLCollection`             | Ideal for targeting elements with specific classes.                                         | Multiple class names can complicate selection; ensure correct class names.       | HTMLCollection is live; updates automatically.                                                 |
| **`querySelector()`**     | Selects the first element that matches a CSS selector.                             | `document.querySelector('.myClass')`                                                                      | `HTMLElement`                | Supports complex selectors; good for precise targeting.                                     | Only returns the first match; use `querySelectorAll` for multiple matches.       | CSS selector syntax must be correct.                                                            |
| **`querySelectorAll()`**  | Selects all elements that match a CSS selector.                                    | `document.querySelectorAll('div.myClass')`                                                                | `NodeList`                   | Use for multiple elements matching a selector.                                             | NodeList is not live; use `HTMLCollection` if you need live updates.              | NodeList is static; doesn't update if DOM changes.                                              |
| **`createElement()`**     | Creates a new HTML element.                                                        | `document.createElement('div')`                                                                           | `HTMLElement`                | Use to dynamically create new elements.                                                     | Ensure correct tag names and attributes.                                         | Newly created elements are not yet part of the DOM.                                              |
| **`appendChild()`**       | Appends a node as the last child of a specified parent node.                       | `parentElement.appendChild(newElement)`                                                                   | `HTMLElement`                | Use to add elements as the last child.                                                        | Avoid appending elements to the wrong parent.                                      | Appends the node at the end of the parent’s child list.                                         |
| **`textContent`**         | Gets or sets the text content of an element.                                       | `element.textContent = 'New text';`                                                                        | `string`                     | Use for plain text updates.                                                                  | Avoid using it for HTML content.                                                     | `textContent` strips out HTML tags, leaving only plain text.                                   |
| **`innerHTML`**           | Gets or sets the HTML content inside an element.                                   | `element.innerHTML = '<p>New content</p>';`                                                                | `string`                     | Useful for setting or getting HTML content.                                                 | Be cautious of XSS vulnerabilities.                                                | `innerHTML` parses the string as HTML; can introduce security issues if content is not sanitized. |
| **`DocumentFragment`**    | A lightweight container to hold DOM nodes temporarily.                             | `let fragment = document.createDocumentFragment();`                                                        | `DocumentFragment`           | Use for batch DOM manipulations.                                                             | Avoid direct manipulation of the fragment if not needed.                          | Fragment is not part of the DOM; must be appended to the DOM.                                    |
| **`after()`**             | Inserts a node after the current node.                                             | `element.after(newElement);`                                                                              | `void`                       | Use for appending content after the element.                                                | Ensure proper positioning of the new element.                                      | Must be called on an existing node.                                                             |
| **`append()`**            | Appends a node as the last child of a specified parent node.                       | `parentElement.append(newElement);`                                                                       | `void`                       | Ideal for adding content at the end of the parent’s child list.                              | Avoid appending multiple nodes simultaneously if the parent needs a single update. | Can append multiple nodes if needed.                                                            |
| **`prepend()`**           | Inserts a node before the first child of a specified parent node.                  | `parentElement.prepend(newElement);`                                                                      | `void`                       | Use to add content at the beginning of the parent’s child list.                              | Avoid using it if the order of nodes is critical.                                  | New node becomes the first child of the parent.                                                 |
| **`insertAdjacentHTML()`**| Parses a text as HTML and inserts it into the document at a specified position.   | `element.insertAdjacentHTML('beforeend', '<p>New paragraph</p>');`                                        | `void`                       | Good for adding HTML snippets relative to an existing element.                              | Ensure correct position values are used.                                            | Can lead to unexpected results if the HTML string is malformed.                                 |
| **`replaceChild()`**      | Replaces a child element with a new element.                                       | `parentElement.replaceChild(newElement, oldElement);`                                                    | `HTMLElement`                | Useful for updating specific child elements.                                                | Be cautious of replacing nodes that may be used elsewhere.                         | Replaces only the first instance found.                                                          |
| **`cloneNode()`**         | Clones an element and its descendants.                                             | `let clone = element.cloneNode(true);`                                                                     | `HTMLElement`                | Use to duplicate an element with or without its children.                                    | Avoid cloning if not necessary, as it can create performance overhead.            | Use `true` for deep cloning; `false` for shallow cloning.                                       |
| **`removeChild()`**       | Removes a child node from a specified parent node.                                | `parentElement.removeChild(childElement);`                                                                | `HTMLElement`                | Use to remove specific child elements.                                                        | Avoid removing nodes that are critical to the layout.                               | The removed node is no longer part of the DOM.                                                  |
| **`insertBefore()`**      | Inserts a new node before an existing node as a child of a specified parent node. | `parentElement.insertBefore(newElement, existingElement);`                                                | `HTMLElement`                | Useful for inserting content at specific locations.                                          | Ensure the reference node exists.                                                    | The new node is inserted before the existing node.                                               |
| **`insertAfter()`**       | Custom helper function to insert a new node after an existing node.               | `insertAfter(newElement, existingElement);` (defined function)                                             | `void`                       | Use to insert content after a specified node.                                                | Ensure proper placement to avoid layout issues.                                    | Requires custom implementation as it's not a standard method.                                  |

### Summary
- **Selecting Elements**: Methods to access specific DOM elements based on different criteria (ID, class, tag name, etc.).
- **Traversing Elements**: Methods to navigate between elements in the DOM tree (parent, child, sibling).
- **Manipulating Elements**: Methods to create, modify, and remove elements in the DOM.

This table should provide a clear overview of what has been learned, how to use each feature, and what to watch out for.
### **Details of Return Types**

- **`HTMLElement`**: Represents a single HTML element.
- **`NodeList`**: Represents a collection of DOM nodes returned by methods like `querySelectorAll()`, `getElementsByName()`, etc. It's not a live collection.
- **`HTMLCollection`**: Represents a collection of HTML elements returned by methods like `getElementsByClassName()` and `getElementsByTagName()`. It's live and updates automatically.
- **`DocumentFragment`**: A lightweight container used to build a document structure off-screen and then insert it into the main DOM tree.
- **`string`**: Represents text content or HTML as a string.
- **`void`**: Indicates that the method does not return a value.

This table should help you understand the different DOM methods and properties along with their usage, examples, and return types.

### Section 4. Manipulating Elements

#### 4.1 createElement()
**Description:**
- `createElement()` is used to create a new element node.

**Code Example:**
```javascript
const newDiv = document.createElement('div');
newDiv.textContent = 'This is a new div created using createElement()';
document.body.appendChild(newDiv);
console.log('Created element:', newDiv);
```

**Return Type:**
- `HTMLElement` - The newly created element.

**Pros:**
- Provides more control over the creation of elements.
- Elements are created programmatically and can be manipulated before being added to the DOM.

**Cons:**
- Requires more code to create and insert content compared to using `innerHTML`.

**Use-Cases:**
- Dynamically adding elements based on user actions.
- Building elements from data fetched from an API.

**Do's:**
- Use for creating complex or multiple elements programmatically.

**Don'ts:**
- Avoid if you need to insert a simple HTML structure quickly.

#### 4.2 appendChild()
**Description:**
- `appendChild()` adds a node to the end of the list of children of a specified parent node.

**Code Example:**
```javascript
const parent = document.getElementById('parent');
const newChild = document.createElement('p');
newChild.textContent = 'This is a new child added using appendChild()';
parent.appendChild(newChild);
console.log('Appended child:', newChild);
```

**Return Type:**
- `Node` - The appended child node.

**Pros:**
- Simple and direct way to add a node to the end of a parent.

**Cons:**
- Can only append one node at a time.

**Use-Cases:**
- Adding new items to a list or table.

**Do's:**
- Use when you need to add a node as the last child.

**Don'ts:**
- Avoid if you need to add multiple nodes at once (use `DocumentFragment` instead).

#### 4.3 textContent
**Description:**
- `textContent` gets or sets the text content of a node and its descendants.

**Code Example:**
```javascript
const element = document.getElementById('example');
console.log('Original text content:', element.textContent);
element.textContent = 'New text content set using textContent';
console.log('Updated text content:', element.textContent);
```

**Return Type:**
- `String` - The text content of the node.

**Pros:**
- Safe from cross-site scripting (XSS) attacks.

**Cons:**
- Removes all child nodes and replaces them with a single text node.

**Use-Cases:**
- Updating the text content of an element.

**Do's:**
- Use when you need to safely update text content.

**Don'ts:**
- Avoid if you need to set HTML content (use `innerHTML`).

#### 4.4 innerHTML
**Description:**
- `innerHTML` gets or sets the HTML content of an element.

**Code Example:**
```javascript
const element = document.getElementById('example');
console.log('Original HTML content:', element.innerHTML);
element.innerHTML = '<strong>New HTML content set using innerHTML</strong>';
console.log('Updated HTML content:', element.innerHTML);
```

**Return Type:**
- `String` - The HTML content of the element.

**Pros:**
- Allows setting complex HTML structures easily.

**Cons:**
- Vulnerable to cross-site scripting (XSS) attacks if not used carefully.

**Use-Cases:**
- Inserting dynamic HTML content fetched from an API.

**Do's:**
- Use carefully and sanitize any user input.

**Don'ts:**
- Avoid inserting untrusted HTML content directly.

#### 4.5 innerHTML vs. createElement
**Description:**
- `innerHTML` sets HTML content directly, while `createElement` allows creating elements programmatically.

**Code Example:**
```javascript
// Using innerHTML
const element1 = document.getElementById('example1');
element1.innerHTML = '<p>Created using innerHTML</p>';
console.log('innerHTML example:', element1.innerHTML);

// Using createElement
const element2 = document.getElementById('example2');
const newPara = document.createElement('p');
newPara.textContent = 'Created using createElement';
element2.appendChild(newPara);
console.log('createElement example:', element2.innerHTML);
```

**Pros of innerHTML:**
- Easier for inserting multiple elements.

**Cons of innerHTML:**
- Vulnerable to XSS attacks.

**Pros of createElement:**
- More control over element creation.

**Cons of createElement:**
- More verbose.

**Use-Cases:**
- `innerHTML` for simple HTML structures.
- `createElement` for complex or dynamic elements.

**Do's:**
- Choose based on the complexity and security requirements.

**Don'ts:**
- Avoid `innerHTML` for untrusted content.

#### 4.6 DocumentFragment
**Description:**
- `DocumentFragment` is a lightweight container for DOM nodes that is not part of the document itself. It is used to build a subtree of DOM elements and insert them all at once.

**Code Example:**
```javascript
const fragment = document.createDocumentFragment();
for (let i = 0; i < 3; i++) {
    const newDiv = document.createElement('div');
    newDiv.textContent = `Fragment div ${i + 1}`;
    fragment.appendChild(newDiv);
}
document.body.appendChild(fragment);
console.log('DocumentFragment:', fragment);
```

**Return Type:**
- `DocumentFragment`

**Pros:**
- Efficiently adds multiple nodes to the DOM.

**Cons:**
- Fragment itself does not exist in the document tree.

**Use-Cases:**
- Adding multiple elements to the DOM at once.

**Do's:**
- Use when adding several elements to improve performance.

**Don'ts:**
- Avoid for single element insertions.

#### 4.7 after()
**Description:**
- `after()` inserts a node after a specified element.

**Code Example:**
```javascript
const referenceNode = document.getElementById('reference');
const newNode = document.createElement('p');
newNode.textContent = 'Inserted after the reference node';
referenceNode.after(newNode);
console.log('Node inserted after reference node:', newNode);
```

**Return Type:**
- `undefined`

**Pros:**
- Easy insertion after a node.

**Cons:**
- Not supported in older browsers.

**Use-Cases:**
- Inserting elements in sequence.

**Do's:**
- Use when you need to insert after a specific element.

**Don'ts:**
- Avoid for complex insertions (use `insertBefore` with next sibling).

#### 4.8 append()
**Description:**
- `append()` inserts a node after the last child of a parent node.

**Code Example:**
```javascript
const parent = document.getElementById('parent');
const newNode = document.createElement('p');
newNode.textContent = 'Appended using append()';
parent.append(newNode);
console.log('Node appended to parent:', newNode);
```

**Return Type:**
- `undefined`

**Pros:**
- Can append multiple nodes or strings.

**Cons:**
- Not supported in older browsers.

**Use-Cases:**
- Adding content to the end of a parent node.

**Do's:**
- Use for appending nodes or strings.

**Don'ts:**
- Avoid if you need compatibility with very old browsers.

#### 4.9 prepend()
**Description:**
- `prepend()` inserts a node before the first child of a parent node.

**Code Example:**
```javascript
const parent = document.getElementById('parent');
const newNode = document.createElement('p');
newNode.textContent = 'Prepended using prepend()';
parent.prepend(newNode);
console.log('Node prepended to parent:', newNode);
```

**Return Type:**
- `undefined`

**Pros:**
- Can prepend multiple nodes or strings.

**Cons:**
- Not supported in older browsers.

**Use-Cases:**
- Adding content to the beginning of a parent node.

**Do's:**
- Use for prepending nodes or strings.

**Don'ts:**
- Avoid if you need compatibility with very old browsers.

#### 4.10 insertAdjacentHTML()
**Description:**
- `insertAdjacentHTML()` parses text as HTML and inserts the resulting nodes into the document at a specified position.

**Code Example:**
```javascript
const element = document.getElementById('example');
element.insertAdjacentHTML('beforeend', '<p>Inserted using insertAdjacentHTML</p>');
console.log('HTML inserted using insertAdjacentHTML');
```

**Return Type:**
- `undefined`

**Pros:**
- Efficient way to insert HTML content.

**Cons:**
- Vulnerable to XSS if not used carefully.

**Use-Cases:**
- Inserting dynamic HTML content.

**Do's:**
- Use for efficient HTML insertion.

**Don'ts:**
- Avoid for untrusted content.

#### 4.11 replaceChild()
**Description:**
- `replaceChild()` replaces a child node with a new node.

**Code Example:**
```javascript
const parent = document.getElementById('parent');
const newNode = document.createElement('p');
newNode.textContent = 'Replaced child using replaceChild()';
const oldNode = parent.children

[0];
parent.replaceChild(newNode, oldNode);
console.log('Replaced child:', newNode);
```

**Return Type:**
- `Node` - The replaced node.

**Pros:**
- Directly replaces a child node.

**Cons:**
- Only works with child nodes.

**Use-Cases:**
- Replacing content based on user actions.

**Do's:**
- Use when replacing specific child nodes.

**Don'ts:**
- Avoid if you need to keep the old node (use `insertBefore` and `removeChild`).

#### 4.12 cloneNode()
**Description:**
- `cloneNode()` creates a copy of a node, optionally including its descendants.

**Code Example:**
```javascript
const original = document.getElementById('original');
const clone = original.cloneNode(true);
document.body.appendChild(clone);
console.log('Cloned node:', clone);
```

**Return Type:**
- `Node` - The cloned node.

**Pros:**
- Creates an exact copy of a node.

**Cons:**
- May require adjustment for unique attributes (e.g., IDs).

**Use-Cases:**
- Duplicating elements for repeated structures.

**Do's:**
- Use for duplicating nodes.

**Don'ts:**
- Avoid if you need a distinct instance (adjust attributes accordingly).

#### 4.13 removeChild()
**Description:**
- `removeChild()` removes a child node from the DOM.

**Code Example:**
```javascript
const parent = document.getElementById('parent');
const child = parent.children[0];
parent.removeChild(child);
console.log('Removed child:', child);
```

**Return Type:**
- `Node` - The removed child node.

**Pros:**
- Directly removes a child node.

**Cons:**
- Only works with child nodes.

**Use-Cases:**
- Removing elements based on user actions.

**Do's:**
- Use for removing specific child nodes.

**Don'ts:**
- Avoid if the node is not a child of the parent.

#### 4.14 insertBefore()
**Description:**
- `insertBefore()` inserts a new node before an existing node.

**Code Example:**
```javascript
const parent = document.getElementById('parent');
const newNode = document.createElement('p');
newNode.textContent = 'Inserted before using insertBefore()';
const referenceNode = parent.children[0];
parent.insertBefore(newNode, referenceNode);
console.log('Node inserted before reference node:', newNode);
```

**Return Type:**
- `Node` - The inserted node.

**Pros:**
- Precise insertion before a reference node.

**Cons:**
- Requires a reference node.

**Use-Cases:**
- Inserting elements in sequence.

**Do's:**
- Use when inserting before a specific node.

**Don'ts:**
- Avoid if reference node is not available.

#### 4.15 insertAfter() helper function
**Description:**
- Helper function to insert a node after a specified node.

**Code Example:**
```javascript
function insertAfter(newNode, referenceNode) {
    referenceNode.parentNode.insertBefore(newNode, referenceNode.nextSibling);
}

const referenceNode = document.getElementById('reference');
const newNode = document.createElement('p');
newNode.textContent = 'Inserted after using insertAfter() helper function';
insertAfter(newNode, referenceNode);
console.log('Node inserted after reference node:', newNode);
```

**Return Type:**
- `undefined`

**Pros:**
- Easy insertion after a node.

**Cons:**
- Requires a reference node.

**Use-Cases:**
- Inserting elements in sequence.

**Do's:**
- Use when you need to insert after a specific element.

**Don'ts:**
- Avoid if reference node is not available.

### Example HTML Document

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM Manipulation Examples</title>
</head>
<body>
    <div id="parent">
        <div id="original">Original Element</div>
    </div>
    <div id="reference">Reference Element</div>

    <script>
        // createElement example
        const newDiv = document.createElement('div');
        newDiv.textContent = 'This is a new div created using createElement()';
        document.body.appendChild(newDiv);
        console.log('Created element:', newDiv);

        // appendChild example
        const parent = document.getElementById('parent');
        const newChild = document.createElement('p');
        newChild.textContent = 'This is a new child added using appendChild()';
        parent.appendChild(newChild);
        console.log('Appended child:', newChild);

        // textContent example
        const element = document.getElementById('original');
        console.log('Original text content:', element.textContent);
        element.textContent = 'New text content set using textContent';
        console.log('Updated text content:', element.textContent);

        // innerHTML example
        const element2 = document.getElementById('reference');
        console.log('Original HTML content:', element2.innerHTML);
        element2.innerHTML = '<strong>New HTML content set using innerHTML</strong>';
        console.log('Updated HTML content:', element2.innerHTML);

        // innerHTML vs. createElement example
        const element3 = document.createElement('div');
        element3.innerHTML = '<p>Created using innerHTML</p>';
        document.body.appendChild(element3);
        console.log('innerHTML example:', element3.innerHTML);

        const element4 = document.createElement('div');
        const newPara = document.createElement('p');
        newPara.textContent = 'Created using createElement';
        element4.appendChild(newPara);
        document.body.appendChild(element4);
        console.log('createElement example:', element4.innerHTML);

        // DocumentFragment example
        const fragment = document.createDocumentFragment();
        for (let i = 0; i < 3; i++) {
            const newDiv = document.createElement('div');
            newDiv.textContent = `Fragment div ${i + 1}`;
            fragment.appendChild(newDiv);
        }
        document.body.appendChild(fragment);
        console.log('DocumentFragment:', fragment);

        // after() example
        const refNode = document.getElementById('reference');
        const newNodeAfter = document.createElement('p');
        newNodeAfter.textContent = 'Inserted after the reference node';
        refNode.after(newNodeAfter);
        console.log('Node inserted after reference node:', newNodeAfter);

        // append() example
        const parentNode = document.getElementById('parent');
        const newNodeAppend = document.createElement('p');
        newNodeAppend.textContent = 'Appended using append()';
        parentNode.append(newNodeAppend);
        console.log('Node appended to parent:', newNodeAppend);

        // prepend() example
        const newNodePrepend = document.createElement('p');
        newNodePrepend.textContent = 'Prepended using prepend()';
        parentNode.prepend(newNodePrepend);
        console.log('Node prepended to parent:', newNodePrepend);

        // insertAdjacentHTML() example
        const element5 = document.getElementById('reference');
        element5.insertAdjacentHTML('beforeend', '<p>Inserted using insertAdjacentHTML</p>');
        console.log('HTML inserted using insertAdjacentHTML');

        // replaceChild() example
        const newNodeReplace = document.createElement('p');
        newNodeReplace.textContent = 'Replaced child using replaceChild()';
        const oldNode = parent.children[0];
        parent.replaceChild(newNodeReplace, oldNode);
        console.log('Replaced child:', newNodeReplace);

        // cloneNode() example
        const original = document.getElementById('original');
        const clone = original.cloneNode(true);
        document.body.appendChild(clone);
        console.log('Cloned node:', clone);

        // removeChild() example
        const child = parent.children[0];
        parent.removeChild(child);
        console.log('Removed child:', child);

        // insertBefore() example
        const newNodeBefore = document.createElement('p');
        newNodeBefore.textContent = 'Inserted before using insertBefore()';
        const referenceNode = parent.children[0];
        parent.insertBefore(newNodeBefore, referenceNode);
        console.log('Node inserted before reference node:', newNodeBefore);

        // insertAfter() helper function example
        function insertAfter(newNode, referenceNode) {
            referenceNode.parentNode.insertBefore(newNode, referenceNode.nextSibling);
        }
        const newNodeInsertAfter = document.createElement('p');
        newNodeInsertAfter.textContent = 'Inserted after using insertAfter() helper function';
        insertAfter(newNodeInsertAfter, refNode);
        console.log('Node inserted after reference node:', newNodeInsertAfter);
    </script>
</body>
</html>
```

This HTML document provides a comprehensive demonstration of various DOM manipulation methods. Each method is explained with comments and console logs to help identify what each example is returning or doing.
