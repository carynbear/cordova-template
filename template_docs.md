#Use a Template

Templates allow you to use preexisting code to jumpstart your project. 

Find a template to create your app from by seaching for the keyword `cordova:template` on [npm](https://www.npmjs.com/search?q=cordova%3Atemplate). You can also use local templates on your computer, or a Git repository.

After locating a template you wish to use. Create your project using that template, by specifying the `--template` flag during the `create` command, followed by your template source.

Creating a cordova project from a template
```
$ cordova create hello com.example.hello HelloWorld --template <npm-package-name | <git-remote-url | local-path>
```

After succesfully using a template to create your project, you'll want to indicate the platforms that you intend to target with your app. Go into your project folder and [add platforms](http://cordova.apache.org/docs/en/latest/guide/cli/index.html#add-platforms).

#Create a Template

Begin by creating a cordova app that will become the basis for your template. Then you'll take the contents of your app and put them into the following structure. When your template is used, all of the contents within `template_src` will be used to create the new project, so be sure to include any necessary files in that folder. Reference [this example](https://github.com/carynbear/cordova-template) for details.

```
template_package/
├── package.json   	(optional; needed to publish template on npm)
├──	index.js 		(required)
└── template_src/ 	(required)
	└── CONTENTS OF APP TEMPLATE
```
Note that `index.js` should export a reference to `template_src` and `package.json` should reference `index.js`. See [the example](https://github.com/carynbear/cordova-template) for details on how that is done.

To finish off your template, edit `package.json` to contain the keyword `"cordova:template"`.
```javascript
{
  ...
  "keywords": [
    "ecosystem:cordova",
    "cordova:template"
  ]
  ...
}
```

Congrats! You've made a template for creating a Cordova project. Share your template on npm so that everyone can benefit from your hard work.
