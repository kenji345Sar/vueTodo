<template>
  <div>
    <ul>
      <li v-for="task in tasks" :key="task.id">
        <ListRow :title="task.title" :checked="task.checked" @update:checked="task.checked = $event"></ListRow>
      </li>
    </ul>
  </div>
</template>

<script>
import { ref } from 'vue';
import ListRow from './components/ListRow.vue';

export default {
  components: {
    ListRow
  },
  setup() {
    const tasks = ref([
      { id: 1, title: "散歩", checked: true },
      { id: 2, title: "料理", checked: false },
      { id: 3, title: "筋トレ", checked: true },
    ]);

    return { tasks };
  },
};
</script>
