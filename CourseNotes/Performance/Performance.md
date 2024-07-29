# Performance

Client makes a request to the server. The client retrieves HTML, CSS, images, JavaScript files, etc., from the server.

This chapter covers ways to enhance performance speed.

## Performance

1. **Improve Client-Side Performance**
2. **Improve Transfer or Network Latency Between Client and Server**
3. **Improve Server-Side Processing**

As a senior developer, it's important to be able to compare improvements to performance.

### Network Performance

- **Honey, I Shrunk the Files**
- **The Traveling Deliveryman**

#### How to Reduce the Size of Your Files?

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