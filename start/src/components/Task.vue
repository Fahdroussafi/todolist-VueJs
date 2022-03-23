<template>
  <div class="container">
    <div class="task">
      <!-- title -->
      <div class="title">
        <h1>To Do List</h1>
      </div>
      <!-- form -->
      <div class="form">
        <input type="text" placeholder="New Task" />
        <button><i class="fas fa-plus"></i></button>
      </div>
      <!-- task lists -->
      <div class="taskItems">
        <ul>
          <li v-for="task in tasks" :key="task.id">
            <button><i class="fas fa-circle"></i> {{ task.title }}</button>
            <button><i class="far fa-trash-alt"></i></button>
          </li>
        </ul>
      </div>
      <!-- buttons -->
      <div class="clearBtns">
        <button>Clear completed</button>
        <button @click="clearAll">Clear all</button>
      </div>
      <!-- pending task -->
      <div class="pendingTasks">
        <span>Pending Tasks: </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Task",
  props:['tasks'],
  methods: {
    clearAll() {
      this.tasks = [];
    }
  },
};
</script>
