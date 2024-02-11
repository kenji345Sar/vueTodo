<!-- ListRow.vue -->
<template>
  <div>
    <input type="checkbox" v-model="localChecked">
    <span :style="localChecked ? 'text-decoration: line-through;' : ''">{{ title }}</span>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    checked: Boolean
  },
  emits: ['update:checked'],
  computed: {
    localChecked: {
      get() {
        return this.checked;
      },
      set(value) {
        this.$emit('update:checked', value);
      }
    }
  }
};
</script>
