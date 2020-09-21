<template>
    <div >
      <form @submit.prevent="addTodo" >
        <input type="text" v-model="title" name="title" placeholder="Add Todo...">
        <!--<input type="submit" value="Submit" class="btn">-->        
        <b-button class="submit " type="submit" variant="btn btn-outline-success">Submit</b-button>
    </form>
   
    </div> 
    

</template>
<script>

export default {
    name:"AddTodo",
    data(){
        return {
            title:''
        }        
    },
    methods: { 

      addTodo() {
      const newTodo = {
        title: this.title,
        completed: false
      }
      // Send up to parent
        this.$emit('add-todo', newTodo);
        this.title = '';
    }
        }
}
</script>

<style scoped>
  form {
    display: flex;
   
  
  }
  input[type="text"] {
    flex: 10;
    padding: 5px;
    outline: none;
  }
  input[type="submit"] {
    flex: 2;
    padding: 5px;
  }

  
  .submit{  
    margin-left: 5px;
    margin-right: 1px;
    min-width: 10em;
  }

input {
  outline: 0;
  border-width: 0 0 2px;
  
}
.btn:focus {
  outline: none;
  box-shadow: none;
}


  ::-webkit-input-placeholder {
       color:silver;
    }
    :-moz-placeholder { /* Upto Firefox 18, Deprecated in Firefox 19  */
       color:silver;
    }
    ::-moz-placeholder {  /* Firefox 19+ */
       color:silver;
    }
    :-ms-input-placeholder {  
       color:silver;
    }
</style>