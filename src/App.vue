<template>
  <main>
    <!-- heading -->
    <header>
      <h3>{{ taskStore.name }} Tasks</h3>
    </header>

    <!-- filter -->
    <nav>
      <button @click="filter = 'all'">All tasks</button>
      <button @click="filter = 'favs'">Fav tasks</button>
    </nav>

    <!-- task list -->
    <div v-if="filter === 'all'">
      <p>Your have {{ taskStore.totalCount }} tasks left to do</p>
      <div v-for="task in taskStore.tasks">
        <TaskDetails :task="task" />
      </div>
    </div>
    <div v-if="filter === 'favs'">
      <p>Your have {{ taskStore.favCount }} tasks left to do</p>
      <div v-for="task in taskStore.favs">
        <TaskDetails :task="task" />
      </div>
    </div>
  </main>
</template>

<script>
import { useTaskStore } from "./stores/TaskStore";
import TaskDetails from "./components/TaskDetails.vue";
import { ref } from "vue";

export default {
  components: {
    TaskDetails,
  },
  setup() {
    const taskStore = useTaskStore();

    const filter = ref("all");

    return { taskStore, filter };
  },
};
</script>

<style scoped></style>
