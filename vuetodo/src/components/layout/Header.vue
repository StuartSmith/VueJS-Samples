<template>
  <header> 
    <div>
    <span class="header"> 
       <div>   
        <HamburgerButton ref="HamburgerButton" v-model ="viewModel.showMenu"  v-on:changedHamburgerButton="ShowHamburgerMenu"/>
        </div> 
           <div>
             <h1> Vue Todo</h1>
           </div>
      </span>      
       <div class="sidenav" v-bind:class="{slidesidenav: viewModel.showMenu}" >          
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
import HamburgerButton from './HamburgerButton.vue'
export default {
  name: "Header",
    data(){
        return {
            viewModel:{
              showMenu:false  
            }
        }                    
    },
   methods: {
    GoHome() {
      this.$refs.HamburgerButton.ToggleHamburgerButton(false);
      this.viewModel.showMenu =false;
      this.$router.push('/').catch(()=>{});
    },
    GoAbout() {
      this.$refs.HamburgerButton.ToggleHamburgerButton(false);
      this.viewModel.showMenu =false;
      this.$router.push('/about').catch(()=>{});
    },
    ShowHamburgerMenu(showMenu)
    {
      
      this.viewModel.showMenu=!showMenu;
    }
    
   },  components: {
    HamburgerButton
    }


}
</script>

<style scoped>

.sidenav {    

  min-width: 150px;  
  position: absolute;
  z-index: 99;
  /*top: 400;*/
  left: -250px;
  background:  rgba(0, 0, 139, 0.90);
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 60px;
  height: 100vh;
  opacity: 10;
}
.headerspacer
{
  height: 60px!important; 
}

.slidesidenav 
{
  transform: translateX(250px);
  transition: transform 250ms ease-in-out;
  position:fixed; 
}

.header {
    background-color: darkblue;
    margin: 0 auto;
    width: 100%;
    max-width: 100%;    
    background-color: darkblue;
    position: fixed;
    height: 60px!important; 
    z-index: 100;   
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

.header {  
    color: #fff;
    text-align: center;   
  }
</style>


