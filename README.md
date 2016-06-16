# Cordova Template Reference
This is a reference for building and publishing Cordova Templates.

## Structure of your template
```
template_package
├── package.json (for your template package to be published on npm)
├──	index.js
└── template_src (contains template files)
    ├── package.json 
	├── config.xml 
	└── (files and folders that make up the template)
```
### Outside of `template_src`
All files outside of `template_src` are used to define parameters about the template. These files are not copied over at creation, so feel free to add a README or any other files outside  of template_src.

`index.js` points to where the template exists. You'll see that index.js usually looks like:
```javascript
var path = require('path');

module.export = {
    dirname = path.join(__dirname, 'template_src')
};
```

`package.json` tells you about the template. It is necessary state that `"main": "index.js"` so that the reference to the template source in `index.js` is propagated. All templates should contain the keyword `"cordova:template"` so that the template is searchable on npm.
```javascript
...
"main": "index.js",
...
"keywords": [
"cordova:template"
...
```

### Inside of `template_src`
All files inside of `template_src` compose the template from which a user would desire in order to create their project. Everything in this folder is copied over to the created project.

(The package.json in `template_src` should be filled with information that describes the project that would be created from the template.)
