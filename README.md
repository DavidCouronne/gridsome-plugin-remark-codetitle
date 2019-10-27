# gridsome-plugin-remark-codetitle
 Adds a code title to code snippets


### settings

in your `gridsome-config.js`

```js
...
transformers: {
    //Add markdown support to all file-system sources
    remark: {
      ...
      plugins: [
          ...
          ['gridsome-plugin-remark-codetitle', {
              className:'your-custom-class-name'
              }], // IMPORTANT: this must be ahead of other plugins that use code blocks
          ['gridsome-plugin-remark-shiki', {
              theme: 'nord'
          }],
          ...
      ]
    }
  }
```


 ## Usage in Markdown

in your Markdown content

``````
```js:title=example-file.js
alert('how cool is this!');
```js
``````

This plug-in analyzes Markdown Tree and converts it into the following structure.

``````
<div class="gridsome-code-title"><span>example-file.js</span></div>
```js
alert('how cool is this');
```
``````
