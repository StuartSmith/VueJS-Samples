<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
  
      <div class="check">
        <b-form-checkbox type="checkbox" v-on:change="markComplete" v-bind:checked="todo.completed"/>
        </div>

      <div  class="message">
               <p> {{todo.title}}</p>
            </div>
      <div class="button">
              <b-button variant="btn btn-outline-danger" @click="$emit('del-todo',todo.id)">X</b-button>
        </div>    
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
}
</script>

<style scoped>
  .todo-item {
    display: flex;
    flex-direction:row;
    background: #fffafa;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }
  .check {   
    min-width: 2em;
  }
  .messaage{    
    justify-content: left;
    
  }
  .button{
    margin-left: auto   
  }
  .is-complete {
    text-decoration: line-through;
  }

  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
</style>

