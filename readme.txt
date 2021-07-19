https://auth0.com/blog/creating-web-components-with-stencil/
https://dev.to/myogeshchavan97/how-to-create-and-publish-an-npm-package-20ln
https://stenciljs.com/docs/angular



1. created a stencil app.
2. created a angular app.
3. now in stencil app generate the build. (which will generate the webcomponent prod code for you to consume) which will be generated in dist folder.
4. in package.json update script to  "main": "dist/index.js",
5. ideally you should publish the code to npm and then consume this as a node module in angular project.
6. to test in local  in you stencil root folder where package.json is placed run "npm link" which will place the bundle in node module global folder
of your pc to consume.


7. now in you angular project go to main.ts add defineCustomElements(); code and register the webcomponent like this
import { defineCustomElements } from 'rating-amogh-component/loader';

8. now go to app.module.ts and set schemas: [CUSTOM_ELEMENTS_SCHEMA] in the NgModule decorator and import CUSTOM_ELEMENTS_SCHEMA; 
this allows angular to run unknown html tags.

9. now in your angular component just use the webcomponent which u created.