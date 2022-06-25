<template>
  <div class="container">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">SIMPLE VUE JS APP</h5>
        <div class="row mb-3">
          <div class="col-10">
            <input @keyup.enter="add" type="text" class="form-control" v-model="todo" />
          </div>
          <div class="col">
            <button class="btn btn-primary" @click="add">Add</button>
          </div>
        </div>
        <div class="row">
           <list :todos="todos" @deleteTodo="deleteTodo"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import List from "./components/List.vue";

export default {
  data() {
    return {
      todo: "",
      todos: [],
    };
  },
  methods : {
    add(){
      this.todos.unshift(this.todo)
      this.todo=""
    },
    deleteTodo(todoIndex){
      this.todos = this.todos.filter((item, index)=>{
        if (index!=todoIndex){
          return item;
        }
      })
    }
  },
  components: {
    List,
  },
};
</script>
