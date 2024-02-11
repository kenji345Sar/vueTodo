<template>
  <div>
    <ul>
      <li v-for="task in tasks" :key="task.id">
        <input type="checkbox" v-model="task.checked">
        <span :style="task.checked ? 'text-decoration: line-through;' : ''">{{ task.title }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
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

<style>
/* 必要に応じてスタイルを追加 */
</style>
