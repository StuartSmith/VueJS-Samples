<template>
  <div class="about">
    <div class="leftBorder"></div>
  <div class="RightContent">
    <h1>About Vue To Do:</h1>
    
<p>This is an example Vue JS To Do application. The application is quite simple, it gives the user the ability
   to add or remove a To Do item from a list of To Do items. It uses Json Place Holder as a mock backend to create and remove a To Do item from a list of To Dos.</p>

<h2>Known issue:</h2>
<p >Since this is a mock API, all new To Do Items will have the same id. Since all new To Do Items have the same ID, 
    adding more than one To Do will cause an error in the console. Also, because each of the new To Do Items share the same ID, if one of the new To Do items is removed from the list of To Dos, 
    all of the new To Do items will be removed. 
  </p>

<p>Below is the error seen in the console.</p>
<p class="redp">[Vue warn]: Duplicate keys detected: '201'. This may cause an update error.<p>

<p class="redp">found in </p>

<p class="redp">---> at src/components/Todos.vue at src/App.vue</p>

<h2>JSON Place Holder</h2>
<p>JSON place holder is a great way for one to get one's feet wet, with calling external web services without having to actually
   create them. These web services are mock web services, where no data is added to them through their web APIs.</p>

<p>The documentation for JSON Place Holder's mock API can be found in the following folder...</p>

<p><a href="https://jsonplaceholder.typicode.com/guide.html">https://jsonplaceholder.typicode.com/guide.html</a></p>

<h3>Steps to Create the To Do Application: </h3>

<h4>1. Create the Vue Application by running the following command line:</h4>
<ul>
  <li>vue create vuetodo</li>
</ul>
<h4>2. Change Vue JS to use relative Paths</h4>
<p>    By default Vue JS assumes that it is going to be at the root project of a URL, which might not be the case. The Vue js application might be in a sub folder of the root project. </p>
<p></p>
 <p>   Add the vue.config.js next to the package.json file with the following content:</p>
<p></p>
   <p>         module.exports = {</p>
      <p>          publicPath: './'</p>
         <p>   }</p>

<h4>3. Use Axios for calls to back end web service calls</h4>
<p>To add Axios to the project run the following npm command line</p>
<ul>
<li>    npm install axios</li>
</ul>

<h4>4. Style Vue JS application with twitter Boot strap. </h4>
<p>Twitter boot strap can give an application a very modern look, to Add twitter bootstrap run the following npm command line </p>
<ul>    
<li>    npm install bootstrap-vue bootstrap</li>
</ul>
<ul>
<li> In the Main JS file add the following: </li>
<p>    import Vue from 'vue'</p>
<p>    import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'</p>

 <p class="comment">   // Install BootstrapVue</p>
 <p>   Vue.use(BootstrapVue)</p>
 <p class="comment">   // Optionally install the BootstrapVue icon components plugin</p>
 <p>   Vue.use(IconsPlugin)</p>

  <p>  import 'bootstrap/dist/css/bootstrap.css'</p>
  <p>  import 'bootstrap-vue/dist/bootstrap-vue.css'</p>
  </ul>
  
  <h4>5. Tutorals Author </h4>
  <p>
     The basic code for this application comes from the following tutorial of by Brad Traversy <a href="https://www.youtube.com/watch?v=Wy9q22isx3U"> "Brad Traversy Crash Course On Vue Js" </a>
  </p>
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

  .comment{
    color:green;
  }

</style>


