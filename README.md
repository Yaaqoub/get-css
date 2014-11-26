# Get CSS
Node module to get CSS from a URL

Returns a promise for an object with details about a document's CSS
Used in http://cssstats.com

## Usage

```js
var getCss = require('get-css');

var options = {
  timeout: 5000
};

getCss('http://github.com', options)
  .then(function(response) {
    console.log(response);
  })
  .catch(function(error) {
    console.error(error);
  });
```

## Response

### `links`
An array of objects base on `rel=stylesheet` links found in the document.

Each object has the following:

- `link` - the value from the `href` attribute for each link tag
- `url` - an absolute url representation of the link
- `css` - the contents of the file in the link

### `styles`
An array of contents from `style` tags found in the document.

### `css`
A concatenated string of all css found in links and styles

### `pageTitle`
The contents of the `title` tag in the document.

