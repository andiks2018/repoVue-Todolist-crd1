<template>
  <ul class="list-group">
    <li v-for="(todo, index) in todos" :key="todo" class="list-group-item">
      <div class="row">
        <div class="col">
          <span>{{ todo }}</span>
        </div>
        <div class="col-auto">
          <div class="row">
            <div class="col">
              <button @click="deleteTODO(index)" class="btn btn-danger">X</button>
            </div>
          </div>
        </div>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    todos: {
      type: Array,
      default: [],
    },
  },
  methods: {
    deleteTODO(index) {
      this.$emit("deleteTodo", index);
    },
  },
};
</script>
