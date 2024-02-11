<template>
  <div>
    <input type="checkbox" :checked="checked" @change="handleChange">
    <span :style="checked ? 'text-decoration: line-through;' : ''">{{ title }}</span>
  </div>
</template>

<script>
import { defineComponent, toRefs } from 'vue';

export default defineComponent({
  props: {
    title: String,
    checked: Boolean,
  },
  setup(props, { emit }) {
    const { checked } = toRefs(props);

    const handleChange = (event) => {
      emit('update:checked', event.target.checked);
    };

    return { checked, handleChange };
  },
});
</script>
