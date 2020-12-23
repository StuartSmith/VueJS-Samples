# Vue To Do

This is an example application using Vue.js as a to do list editor. The application is quite simple, using Json Place Holder as a Mock backend to create and remove To-Do's from a list of To-Do items. 


![Alt text](https://github.com/StuartSmith/VueJS-Samples/blob/master/vuetodo/GitHubImage/2020-10-07%2020-54-33.gif?raw=true "VueJS To Do Application")

### Known issue:   
Since this is a Mock API, creating more than one To-Do, will cause an error where multiple To-Do's with the same ID will be generated and added to the list of To-Do elements. 

**[Vue warn]: Duplicate keys detected: '201'. This may cause an update error.**

**found in**

**---> <Todos> at src/components/Todos.vue**
        **<App> at src/App.vue**
       **<Root>**

### JSON Place Holder
JSON place holder is a great way for one to get's one feet web calling external web services. These web service are mock web services where no new true data is added to them through their web APIs. 

The documentation for JSON Place holder Mock API can be found in the following folder...

    https://jsonplaceholder.typicode.com/guide.html


## Steps to create the to do application


    1.Create the Vue Application by running the following command line:
         vue create vuetodo

    2. Add the vue Router...
        History Mode and the view router:
        History mode when enabled  removes the need of hashes from the URL, which looks more professional then when the hashes
        are included. The issue found, is that history mode only works if running Vue.js from a web server 
        and not from files locally stored on disk.  Since this project runs using files stored locally on disk
        History mode must be disabled.  
        
        The URL when history mode is not enabled looks as follows:         
              vuetodo/dist/index.html**#**/         
         It is not as clean as when history mode is enabled        
              vuetodo/dist/index.html/       
       
        To create the vue router with history mode turned off, use the option of N. 
         

    3. When building for production remove the /slash in hrefs
        By default Vue JS assumes that it is going to be at the root project of a URL, which might not be the case. 
        The Vue.Js application might be in a sub folder of the root project. 

        Add the vue.config.js next to the package.json file with the following content:

                module.exports = {
                    publicPath: './'
                }

    4. This application uses Axios for Rest Calls back to the Json Place holder web site. 
    
    To install Axios run the following command 
        * npm install axios

    5. This application uses twitter boot strap for styling. There are many vue boot strap npm packages to use but for this project,
    npm package bootstrap-vue was settled on. This project only touched the surface on what is possible with twitter bootstrap styling. 
        
    To install bootstrap-vue run the following command     
        npm install bootstrap-vue bootstrap

       To style the Application add the following to the Main.js:

              import Vue from 'vue'
              import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'

              // Install BootstrapVue
              Vue.use(BootstrapVue)
              // Optionally install the BootstrapVue icon components plugin
              Vue.use(IconsPlugin)

              import 'bootstrap/dist/css/bootstrap.css'
              import 'bootstrap-vue/dist/bootstrap-vue.css'

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
