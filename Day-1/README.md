# Summary:

# Notes:   
Recreating the portfolio site.   
Refference: https://mattfarley.ca/   
Today's Goal: Navbar

## HTML and CSS Project Folder Structure

### Folder Structure

```
project-root/
│
├── index.html
├── css/
│   └── styles.css
├── images/
│   └── example.jpg
├── js/
│   └── scripts.js
└── README.md
```

### Explanation of Each Part

1. **`index.html`**: The main HTML file of your project.
2. **`css/`**: Directory for all CSS files.
   - **`styles.css`**: Main CSS file.
3. **`images/`**: Directory for images used in your project.
4. **`js/`**: Directory for JavaScript files (optional if you're only working with HTML and CSS initially).
   - **`scripts.js`**: Main JavaScript file.
5. **`README.md`**: A markdown file to describe your project, how to set it up, and any other relevant information.

### Best Practices

1. **Use Clear and Consistent Naming Conventions**:
   - Use lowercase letters and hyphens for file and folder names (`styles.css`, `index.html`).
   
2. **Organize by Type**:
   - Group files by their type (e.g., CSS files in the `css/` folder, images in the `images/` folder).
   
3. **Separate Concerns**:
   - Keep HTML, CSS, and JavaScript files separate to maintain a clear structure.
   
4. **README File**:
   - Include a `README.md` file to provide an overview of the project, setup instructions, and any other relevant information.

## Leanred about **box-Sizing: border-box**
Certainly! Let’s delve deeper into `box-sizing: border-box;` with detailed examples to illustrate its effect on element dimensions.

### Default `box-sizing: content-box;`

By default, elements use `box-sizing: content-box;`. Let's see how this works with an example.

#### Example 1: `box-sizing: content-box;`

HTML:
```html
<div class="box-content-box">Content-box</div>
```

CSS:
```css
.box-content-box {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 10px solid black;
  box-sizing: content-box; /* Default value, can be omitted */
  background-color: lightblue;
}
```

**Calculations:**

- **Width**: 200px (content) + 40px (padding: 20px on each side) + 20px (border: 10px on each side) = 260px
- **Height**: 100px (content) + 40px (padding: 20px on top and bottom) + 20px (border: 10px on top and bottom) = 160px

In the `content-box` model, the specified width and height only account for the content area. Padding and border are added outside these dimensions, making the actual size of the element larger than specified.

### `box-sizing: border-box;`

Now, let’s see how the `border-box` model changes these calculations.

#### Example 2: `box-sizing: border-box;`

HTML:
```html
<div class="box-border-box">Border-box</div>
```

CSS:
```css
.box-border-box {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 10px solid black;
  box-sizing: border-box;
  background-color: lightcoral;
}
```

**Calculations:**

- **Width**: 200px (includes content, padding, and border)
  - **Content Width** = 200px - 40px (padding: 20px on each side) - 20px (border: 10px on each side) = 140px
- **Height**: 100px (includes content, padding, and border)
  - **Content Height** = 100px - 40px (padding: 20px on top and bottom) - 20px (border: 10px on top and bottom) = 40px

In the `border-box` model, the specified width and height include the content, padding, and border. This makes the element’s total size exactly what you set, regardless of the padding and border.

### Applying `box-sizing: border-box;` Globally

To simplify layout management, it’s common to apply `box-sizing: border-box;` to all elements globally.

#### Example 3: Global `border-box`

HTML:
```html
<div class="box-global">Global Border-box</div>
```

CSS:
```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

.box-global {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 10px solid black;
  background-color: lightgreen;
}
```

**Calculations:**

- **Width**: 200px (includes content, padding, and border)
  - **Content Width** = 200px - 40px (padding: 20px on each side) - 20px (border: 10px on each side) = 140px
- **Height**: 100px (includes content, padding, and border)
  - **Content Height** = 100px - 40px (padding: 20px on top and bottom) - 20px (border: 10px on top and bottom) = 40px

This approach ensures that all elements in your project use the `border-box` model, making it easier to manage sizes and layouts consistently across your entire application.

### Summary

- **`content-box` (default)**: Width and height only include the content. Padding and border are added outside these dimensions.
- **`border-box`**: Width and height include the content, padding, and border. This makes the total size of the element exactly what you set, simplifying layout calculations.   

Using `border-box` helps ensure that the elements' sizes remain predictable, making your layout more consistent and easier to manage, especially in complex or responsive designs.   

## Flex Diaplay   

Certainly! `display: flex` is a powerful CSS property that makes it easier to design flexible and responsive layout structures without having to use floats or positioning. It enables a flex container, which can arrange its children in a way that adapts to different screen sizes and orientations.

### Understanding `display: flex`

When you apply `display: flex` to a container, it becomes a flex container, and its children become flex items. The flex container provides a way to align and distribute space among the items inside it, using a more efficient and predictable approach than traditional layout methods.

### Basic Properties

Here are the fundamental properties associated with `display: flex`:

1. **Flex Container Properties:**
   - `display: flex;`: Defines a flex container.
   - `flex-direction`: Establishes the main axis (horizontal or vertical).
   - `justify-content`: Aligns items along the main axis.
   - `align-items`: Aligns items along the cross axis.
   - `align-content`: Aligns rows of items (used when there are multiple rows).

2. **Flex Item Properties:**
   - `flex-grow`: Defines the ability for a flex item to grow if necessary.
   - `flex-shrink`: Defines the ability for a flex item to shrink if necessary.
   - `flex-basis`: Defines the default size of an element before the remaining space is distributed.
   - `align-self`: Allows the default alignment to be overridden for individual flex items.

### Examples

#### Example 1: Basic Flex Container

HTML:
```html
<div class="flex-container">
  <div class="flex-item">Item 1</div>
  <div class="flex-item">Item 2</div>
  <div class="flex-item">Item 3</div>
</div>
```

CSS:
```css
.flex-container {
  display: flex;
  border: 1px solid #000;
}

.flex-item {
  padding: 20px;
  border: 1px solid #000;
  background-color: lightblue;
}
```

In this example, the `.flex-container` will arrange its child `.flex-item` elements in a row (the default direction).

#### Example 2: Flex Direction

You can change the direction of the flex items with `flex-direction`.

CSS:
```css
.flex-container-column {
  display: flex;
  flex-direction: column;
  border: 1px solid #000;
}
```

This changes the layout to a column.

#### Example 3: Justify Content

You can align items along the main axis using `justify-content`.

CSS:
```css
.flex-container-space-between {
  display: flex;
  justify-content: space-between;
  border: 1px solid #000;
}

.flex-container-center {
  display: flex;
  justify-content: center;
  border: 1px solid #000;
}
```

- `space-between`: Distributes items with space between them.
- `center`: Centers items along the main axis.

#### Example 4: Align Items

Align items along the cross axis using `align-items`.

CSS:
```css
.flex-container-align-center {
  display: flex;
  align-items: center;
  height: 200px; /* To see the vertical alignment */
  border: 1px solid #000;
}
```

- `align-items: center;`: Centers items along the cross axis.

#### Example 5: Flex Grow, Shrink, and Basis

Control how items grow and shrink with `flex-grow`, `flex-shrink`, and `flex-basis`.

CSS:
```css
.flex-item-grow {
  flex-grow: 1; /* Grow to fill space */
  padding: 20px;
  border: 1px solid #000;
  background-color: lightgreen;
}
```

HTML:
```html
<div class="flex-container-grow">
  <div class="flex-item-grow">Item 1</div>
  <div class="flex-item-grow">Item 2</div>
  <div class="flex-item-grow">Item 3</div>
</div>
```

Here, each `.flex-item-grow` will grow to equally fill the available space.

### Detailed Example: Combining Properties

Let's combine several flex properties to create a more complex layout.

HTML:
```html
<div class="flex-container-complex">
  <div class="flex-item">Item 1</div>
  <div class="flex-item">Item 2</div>
  <div class="flex-item">Item 3</div>
  <div class="flex-item">Item 4</div>
  <div class="flex-item">Item 5</div>
</div>
```

CSS:
```css
.flex-container-complex {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  height: 200px; /* To see the vertical alignment */
  border: 1px solid #000;
}

.flex-item {
  padding: 20px;
  border: 1px solid #000;
  background-color: lightcoral;
  flex-grow: 1; /* Each item will grow to fill the space equally */
  margin: 5px; /* Add some space around items */
}
```

### Summary

- **`display: flex`** creates a flex container, enabling the use of flexbox properties.
- **`flex-direction`** determines the direction of the main axis (row or column).
- **`justify-content`** aligns items along the main axis.
- **`align-items`** aligns items along the cross axis.
- **`flex-grow`, `flex-shrink`, and `flex-basis`** control how flex items grow, shrink, and are sized.

Using `display: flex` and its associated properties makes it much easier to create flexible and responsive layouts, avoiding the need for complex float or positioning hacks.   

---

# Key Terminologies

