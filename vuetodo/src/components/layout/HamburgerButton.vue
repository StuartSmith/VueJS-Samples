<template>
    <div>   
         <input type="checkbox" class="openSidebarMenu" id="openSidebarMenu" v-model ="viewModel.showMenu" @click="ChangedHamburgerButton">        
          <label for="openSidebarMenu" class="sidebarIconToggle">
            <div class="spinner diagonal part-1"></div>
            <div class="spinner horizontal"></div>
            <div class="spinner diagonal part-2"></div>
          </label>       
        </div> 
</template>
<script>

export default {
    name: "HamburgerButton",
    data(){
        return {
            viewModel:{
              showMenu:false  
            }
        }                
    },
    methods: {
        ChangedHamburgerButton() {
            this.$emit('changedHamburgerButton',this.viewModel.showMenu)
        },
        ToggleHamburgerButton(showMenu){
            this.viewModel.showMenu = showMenu;
        }       
    },
    watch:{
       showMenu:function(val)
        {
            this.$emit("ShowHamburgerMenu",val)
        },deep:true
    }
}
</script>
<style scoped>

.openSidebarMenu{
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
    transition: all 0.0s;
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
    transition: all 0.0s;
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
</style>
