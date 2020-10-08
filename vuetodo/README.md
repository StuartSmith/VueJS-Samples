# Vue To Do

This is an example application using Vue.js as a to do list editor. The application is quite simple, using Json Place Holder as a Mock backend to create and remove to do's from a list of to do items. 


![Alt text](https://github.com/StuartSmith/VueJS-Samples/blob/master/vuetodo/GitHubImage/2020-10-07%2020-54-33.gif?raw=true "VueJS To Do Application")

### Known issue:   
Since this is a Mock API, creating more than one to do, will cause an error where multiple to dos with the same ID will be generated and added to the list of to do elements. 

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

    2. Add the vie Router...
        There are two options for the view router.
            Do not use History mode with the view Router
                Is to create the vue router with history mode turned off ie use the option of N, This will put a hash in the routes so vue knows that a router is enabled.
                for example the route will look like so...
                    vuetodo/dist/index.html**#**/
                Since this demo application will not be run from a web server, we will use the hash option for history mode to be disabled. This does not look as good as having no slash but with out a web server this is the best option 
            
            Use history mode
                
                This looks better to the end user than having history mode enabled the issue. There is no hash in the URL
                    vuetodo/dist/index.html/ 
                
                But for this to functon properly, must run vue from a web server


    3. When building for production remove the /slash in hrefs
        By default Vue JS assumes that it is going to be at the root project of a URL, which might not be the case. The Vue js application might be in a sub folder of the root project. 

        Add the vue.config.js next to the package.json file with the following content:

                module.exports = {
                    publicPath: './'
                }

    4. Use Axios for calls to back end web service calls
        npm install axios

    5. Style Vue JS application with twitter Boot strap. 
        
        npm install bootstrap-vue bootstrap

    In the Main JS file add the following: 

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
