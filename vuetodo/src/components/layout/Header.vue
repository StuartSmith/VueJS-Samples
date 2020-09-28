<template>
  <header> 
    <div>
    <span class="header"> 
       <div>   
         <input type="checkbox" class="openSidebarMenu" id="openSidebarMenu" v-model="showMenu">        
          <label for="openSidebarMenu" class="sidebarIconToggle">
            <div class="spinner diagonal part-1"></div>
            <div class="spinner horizontal"></div>
            <div class="spinner diagonal part-2"></div>
          </label>
        </div> 
           <div>
             <h1> Vue Todo</h1>
           </div>
      </span>      
       <div class="sidenav" v-bind:class="{ slidesidenav: showMenu}" >
          <ul class="sidebarMenuInner">
            <li @click="GoHome">Home</li>
            <li @click="GoAbout">About</li>
          </ul>
        </div>
      <div class="headerspacer"></div>
      <router-view/>
      </div>     
  </header>
</template>

<script>
export default {
  name: "Header",
    data(){
        return {
            showMenu:false
        }                
    },
   methods: {
    GoHome() {
      this.showMenu=false;
      this.$router.push('/').catch(()=>{});
    },
    GoAbout() {
      this.showMenu=false;
      this.$router.push('/about').catch(()=>{});
    }
   }

}
</script>

<style scoped>

.sidenav {
  height: 100%;
  min-width: 150px;  
  position: absolute;
  z-index: 100;
  top: 0;
  left: -250px;
  background:  darkblue;
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 60px;
}

.slidesidenav 
{
  transform: translateX(250px);
  transition: transform 250ms ease-in-out; 
}

.headerspacer
{
  height: 60px!important;
}

.header {
    display: grid;
    margin: 0 auto;
    width: 100%;
    max-width: 100%;
    box-shadow: none;
    background-color: darkblue;
    position: fixed;
    height: 60px!important;
    overflow: hidden;
    z-index: 101;
    opacity: 50;
}
.main {
    margin: 0 auto;
    display: block;
    height: 100%;
    margin-top: 60px;
}
.mainInner{
    display: table;
    height: 100%;
    width: 100%;
    text-align: center;
}
.mainInner div{
    display:table-cell;
    vertical-align: middle;
    font-size: 3em;
    font-weight: bold;
    letter-spacing: 1.25px;
}
#sidebarMenu {
    height: 100%;
    position: fixed;
    left: 0;
    width: 150px;
    margin-top: 60px;
    transform: translateX(-150px);
    transition: transform 250ms ease-in-out;
    background: darkslategray;
    border-top: 2px solid slategray;
}
.sidebarMenuInner{
    margin:0;
    padding:0;   
    border-top: 2px solid slategray;    
}



.sidebarMenuInner li{
    list-style: none;
    color: #fff;
    text-transform: uppercase;
    font-weight: bold;
    padding: 20px;
    cursor: pointer;
    border-bottom: 2px solid slategray;
}
.sidebarMenuInner li span{
    display: block;
    font-size: 14px;
    color: rgba(255, 255, 255, 0.50);
}

.sidebarMenuInner li a{
    color: #fff;
    text-transform: uppercase;
    font-weight: bold;
    cursor: pointer;
    text-decoration: none;
}

 li:hover{
  color: black;
  background:lightslategray;
}

input[type=checkbox] {
    transition: all 0.3s;
    box-sizing: border-box;
    display: none;
}
.sidebarIconToggle {
    transition: all 0.3s;
    box-sizing: border-box;
    cursor: pointer;
    position: absolute;
    z-index: 99;
    height: 100%;
    width: 100%;
    top: 22px;
    left: 15px;
    height: 22px;
    width: 22px;
}
.spinner {
    transition: all 0.3s;
    box-sizing: border-box;
    position: absolute;
    height: 3px;
    width: 100%;
    background-color: #fff;
}
.horizontal {
    transition: all 0.3s;
    box-sizing: border-box;
    position: relative;
    float: left;
    margin-top: 3px;
}
.diagonal.part-1 {
    position: relative;
    transition: all 0.3s;
    box-sizing: border-box;
    float: left;
}
.diagonal.part-2 {
    transition: all 0.3s;
    box-sizing: border-box;
    position: relative;
    float: left;
    margin-top: 3px;
}

input[type=checkbox]:checked ~ .sidebarIconToggle > .horizontal {
    transition: all 0.3s;
    box-sizing: border-box;
    opacity: 0;
}
input[type=checkbox]:checked ~ .sidebarIconToggle > .diagonal.part-1 {
    transition: all 0.3s;
    box-sizing: border-box;
    transform: rotate(135deg);
    margin-top: 8px;
}
input[type=checkbox]:checked ~ .sidebarIconToggle > .diagonal.part-2 {
    transition: all 0.3s;
    box-sizing: border-box;
    transform: rotate(-135deg);
    margin-top: -9px;
}

  .header {  
    color: #fff;
    text-align: center;   
  }

  

  



</style>


