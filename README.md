# lazy

This is an advanced lazy loading library for dynamically loading images as they come into view using the Intersection Observer API.

## Usage

1. **Include the Library**:

   Download the [`lazyLoad.js`](./lazyLoad.js) file and include it in your project.

2. **Import the Function**:

   Import the `lazyLoadImages` function in your main JavaScript file:

   ```javascript
   import { lazyLoadImages } from './lazyLoad.js';
   ```

3. **Initialize Lazy Loading**:

   Call the `lazyLoadImages` function with a CSS selector for the images you want to lazy load and any custom options:

   ```javascript
   document.addEventListener('DOMContentLoaded', () => {
     lazyLoadImages('.lazy-image', { threshold: 0.7 });
   });
   ```

4. **HTML Markup**:

   In your HTML, use the `data-src` attribute to specify the image source and add a class (e.g., `lazy-image`) for targeting:

   ```html
   <img class="lazy-image" data-src="path_to_your_image.jpg" src="placeholder.jpg" alt="Description">
   ```

### How It Works

The library utilizes the Intersection Observer API to monitor when elements become visible within the viewport. When an image comes into view, its `src` attribute is set to the value of `data-src`, effectively loading the image.

### Custom Options

- `selector`: CSS selector for the images to be lazy loaded.
- `options`: An object with optional settings. Default includes a threshold of 0.5 (meaning 50% of the element must be visible for the callback to trigger).

## Example Usage

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lazy Loading Example</title>
</head>
<body>

<img class="lazy-image" data-src="image1.jpg" src="placeholder.jpg" alt="Image 1">
<img class="lazy-image" data-src="image2.jpg" src="placeholder.jpg" alt="Image 2">
<!-- Add more lazy-loaded images as needed -->

<script src="lazyLoad.js"></script>
<script>
  document.addEventListener('DOMContentLoaded', () => {
    lazyLoadImages('.lazy-image', { threshold: 0.7 });
  });
</script>

</body>
</html>
```

## Additional Notes

- Ensure that the browser supports the Intersection Observer API. If not, consider adding a polyfill for wider compatibility.

- Adjust the threshold value and other options as needed for your specific use case.

- This library focuses on lazy loading images, but it can be extended for other elements or functionalities based on similar principles.
