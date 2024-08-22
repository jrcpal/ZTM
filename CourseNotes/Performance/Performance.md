# Performance

When a client makes a request to the server, it retrieves HTML, CSS, images, JavaScript files, etc., from the server. This chapter covers ways to enhance performance speed.

## Key Areas of Performance Improvement

1. **Improve Client-Side Performance**
2. **Improve Transfer or Network Latency Between Client and Server**
3. **Improve Server-Side Processing**

As a senior developer, it's important to be able to compare improvements to performance.

### Network Performance

- **Honey, I Shrunk the Files**
- **The Traveling Deliveryman**

#### How to Reduce the Size of Your Files

##### Minimize Text

- **UglifyJS**: Reduces whitespace and indentation to minimize text files.

##### Minimize Images

- **Changing Image File Format**: Can help reduce file size.
  - **JPG**: Used mostly for photos and images with many colors. Does not allow for transparent backgrounds.
  - **GIF**: Limits the number of colors, which helps reduce the size of the animation.
  - **PNG**: Limits the number of colors and is usually smaller in size. Allows for transparency.
  - **SVG**: Simplistic vector graphic files that maintain sharpness in size expansion and can be customized.

- **Tools to Reduce Image Size**:
  - **Reduce PNG with TinyPNG**
  - **Reduce JPG with JPEG-optimizer**
  - **Always lower JPG image quality**

## Media Queries

Media Queries can be used to apply CSS styles to images and control image size according to the device. The browser is smart enough to know to only download images/files that it needs.

- **MediaQuery Cheat Sheet**: [gist.github.com/bartholomej/8415655](https://gist.github.com/bartholomej/8415655)

## CDNs - Content Delivery Network

Tools like imgix store images for you and return optimized and cached versions of the images.

## Remove Image Metadata

Data attached to images, such as location, camera details, etc., take up extra size and can be removed on sites such as [verexif.com](https://www.verexif.com/en/).

## Reducing Download Frequency

Beyond reducing file size, we can minimize how often or how many files are sent.

### Critical Render Path

1. **DOM Creation**:
   - The DOM (Document Object Model) is created once the HTML file is received.
   - The DOM describes the content of the page.

2. **CSSOM Creation**:
   - The DOM receives the CSS file.
   - The DOM also generates a CSS tree model called the CSSOM (CSS Object Model) while the HTML model is being generated.

3. **JavaScript Execution**:
   - The DOM reads the JavaScript file.

4. **Render Tree Model**:
   - The browser combines the HTML DOM and CSSOM into a render tree model.

5. **Page Layout and Painting**:
   - The DOM renders the page layout.
   - The DOM then paints the page.
   - Images are downloaded in the background.

### HTML Best Practices

- **CSS Loading**:
  - Best practice is to send CSS files to the browser as soon as possible.
  - Delay sending JS files to the browser to give time to create the CSSOM.
  - Achieve this by linking JS scripts beneath the link to the style sheets.

### CSS Best Practices

- **Render Blocking**:
  - CSS is render-blocking because the CSSOM needs to complete first to generate the render tree.

- **Techniques to Reduce CSS Loading Time**:
  - Load only what is needed.
  - Load 'above the fold': Prioritize content that will be seen first at page load.
  - Use media queries and attributes to avoid disrupting page load if the screen doesn't match. For example:
    ```html
    <link rel="stylesheet" href="./style2.css" media="only screen and (min-width:500px)">
    ```

### JavaScript Best Practices

- **Using `async`**:
  - `async` can execute at any time, before the page finishes loading or too late, which can cause errors or a subpar experience.
  - Best to add `async` to scripts that don't affect the DOM or CSSOM, such as items that don't rely on your code or directly affect user experience.
  - Use if core functionality requires a JavaScript library.

- **Using `defer`**:
  - `defer` is similar to `async`, but it will wait to execute until after the HTML has been parsed.