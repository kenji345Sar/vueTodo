
<template>
  <div id="app">
    <ListRow v-for="task in tasks" :key="task.id" :task="task.title" :isCheck="task.checked" @toggle="toggleTask" />
  </div>
</template>

<script>
import ListRow from './components/ListRow.vue';

export default {
  components: {
    ListRow
  },
  data() {
    return {
      tasks: [
        { id: 1, title: '散歩', checked: true },
        { id: 2, title: '料理', checked: false },
        { id: 3, title: '筋トレ', checked: true },
      ],
    };
  },
  methods: {
    toggleTask(taskTitle) {
      const task = this.tasks.find(t => t.title === taskTitle);
      if (task) {
        task.checked = !task.checked;
      }
    },
  },
};
</script>

