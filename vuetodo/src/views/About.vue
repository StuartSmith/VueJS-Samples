<template>
  <div class="about">
    <div class="leftBorder"></div>
  <div class="RightContent">
    <h1>Vue Todo</h1>
<p>This is an example application using Vue JS as a To Do application. The application is quite simple, using Json Place Holder as a Mock backend to create and remove todos from a list of todo items.</p>

<h2>Known issue:</h2>
<p >Since this is a Mock API, creating more than one todo, will cause an error where multiple todos with the same ID will be generated and added to the list of todos elements:<p>

<p class="redp">[Vue warn]: Duplicate keys detected: '201'. This may cause an update error.<p>

<p class="redp">found in </p>

<p class="redp">---> at src/components/Todos.vue at src/App.vue</p>

<h2>JSON Place Holder</h2>
<p>JSON place holder is a great way for one to get's one feet web calling external web services. These web service are mock web services where no new true data is added to them through their web APIs.</p>

<p>The documentation for JSON Place holder Mock API can be found in the following folder...</p>

<p><a href="https://jsonplaceholder.typicode.com/guide.html">https://jsonplaceholder.typicode.com/guide.html</a></p>
<p>Steps to create the Todo application </p>
<h4>1. Create the Vue Application by running the following command line:</h4>
<p>     vue create vuetodo</p>

<h4>2. When building for production remove the /slash in hrefs</h4>
<p>    By default Vue JS assumes that it is going to be at the root project of a URL, which might not be the case. The Vue js application might be in a sub folder of the root project. </p>
<p></p>
 <p>   Add the vue.config.js next to the package.json file with the following content:</p>
<p></p>
   <p>         module.exports = {</p>
      <p>          publicPath: './'</p>
         <p>   }</p>

<h4>3. Use Axios for calls to back end web service calls</h4>
<p>    npm install axios</p>

<h4>4. Style Vue JS application with twitter Boot strap. </h4>
    
<p>    npm install bootstrap-vue bootstrap</p>

<p>In the Main JS file add the following: </p>

<p>    import Vue from 'vue'</p>
<p>    import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'</p>

 <p>   // Install BootstrapVue</p>
 <p>   Vue.use(BootstrapVue)</p>
 <p>   // Optionally install the BootstrapVue icon components plugin</p>
 <p>   Vue.use(IconsPlugin)</p>

  <p>  import 'bootstrap/dist/css/bootstrap.css'</p>
  <p>  import 'bootstrap-vue/dist/bootstrap-vue.css'</p>
  </div>
   </div>
</template>

<style>
 .about
  {
    display: flex;
  }

  .leftBorder
  {
    min-width: 2em;
  }
  .RightContent p
  {
    padding-left: 2em;
  }

  .redp{
    color:red;
    font-weight: bold;
    
  }

</style>


