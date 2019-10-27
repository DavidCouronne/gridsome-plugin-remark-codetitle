# gridsome-plugin-remark-codetitle
 Adds a code title to code snippets

 ![example](https://github.com/DavidCouronne/gridsome-plugin-remark-codetitle/blob/master/snapshot.png)

## Install

```bash
npm install gridsome-remark-prismjs-title --save-dev
```

## Settings

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
          '@gridsome/remark-prismjs'
          ...
      ]
    }
  }
```


 ## Usage in Markdown

in your Markdown content

``````
```js:title=example-file.js
const visit = require('unist-util-visit');
```js
``````

This plug-in analyzes Markdown Tree and converts it into the following structure.

``````
<div class="gridsome-code-title"><span>example-file.js</span></div>
```js
const visit = require('unist-util-visit');
```
``````

## Add CSS


The following is an example of using `solarized` for` prism.js` style.


```css
.gridsome-code-title {
    display: block;
    position: relative;
    background: #fffbf3;
    width: 100%;
    top: 10px;
    border-top-left-radius: 0.3em;
    border-top-right-radius: 0.3em;
  }
  
  .gridsome-code-title span {
    display: inline;
    position: relative;
    font-size: .85em;
    font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace;
    color: #232129;
    background: rgb(247, 223, 30);
    border-top-left-radius: 0.3em;
    border-bottom-right-radius: 0.3em;
    padding: 3px;
    top: 1px;
  }
```
