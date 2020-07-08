<template>
  <div>
    <div>TodoList</div>
    <div v-for="task in tasks" :key="task.name">
        <div class="name">名前: {{ task.name }}</div>
        <div class="deadline">期限: {{task.deadline}}</div>
        <div class="number"></div>
        <div v-if="task.number==0"><div class="button"><button @click="task.number++">finish </button></div></div>
        <div v-if="task.number>=1">完了 </div>
    </div>
    <div>
      <label>
        名前
        <input type="text" v-model="newTaskName">
      </label>
      <label>
        期限
        <input type="text" v-model="newTaskDeadline">
      </label>
      <button @click="addTask">add</button>
    </div>
  </div>
</template>

<style></style>

<script>
export default {
  name: "TodoList",
  data() {
    return {
      tasks: [],
      newTaskName: "",
      newTasknumber: 0
    };
  },
  methods: {
    addTask() {
      this.tasks.push({ name: this.newTaskName ,deadline: this.newTaskDeadline , number: this.newTasknumber});
    }
  }
};
</script>