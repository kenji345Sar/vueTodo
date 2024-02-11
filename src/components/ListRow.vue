<template>
  <div @click="handleClick">
    <span v-if="isCheck">☑︎</span>
    <span v-else>□</span>
    <span :style="{ textDecoration: isCheck ? 'line-through' : 'none' }">{{ task }}</span>
  </div>
</template>

<script>
export default {
  props: {
    task: String,
    isCheck: Boolean
  },
  methods: {
    handleClick() {
      this.$emit('toggle', this.task);
    }
  }
};
</script>
