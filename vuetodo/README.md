# vuetodo

This is a demo example vue app.

This app was created running the Vue CLI

Steps 

    1.Create the Vue Application by running the following command line:
         vue create vuetodo

    2. When building for production remove the /slash in hrefs
        By default Vue JS assumes that it is going to be at the root project of a URL, which might not be the case. The Vue js application might be in a sub folder of the root project. 

        Add the vue.config.js next to the package.json file with the following content:

                module.exports = {
                    publicPath: './'
                }

    3. Use Axios for calls to back end web service calls
        npm install axios

    4. Style Vue JS application with twitter Boot strap. 
        
        npm install bootstrap-vue bootstrap

    In the Main JS file add the following 

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
