<template>
  <div class="input-group mb-3">
    <input
      type="text"
      class="form-control"
      v-model="newTodo.title"
      placeholder="Enter new todo"
    />
    <div class="input-group-append">
      <button class="btn btn-dark" @click="addedTodo">Add Todo</button>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  data() {
    return {
      newTodo: {
        title: "",
        completed: false,
      },
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    addedTodo() {
      this.addTodo(this.newTodo);
      this.newTodo.title = "";
    },
  },
};
</script>

<style>
</style>