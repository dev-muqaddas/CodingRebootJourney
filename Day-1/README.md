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

---

# Key Terminologies
---
