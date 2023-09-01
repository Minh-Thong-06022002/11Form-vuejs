<template>
  <ul>
    <li>
      <button
        :class="{ active: modelValue === 'poor' }"
        type="button"
        @click="active('poor')"
      >
        Poor
      </button>
    </li>
    <li>
      <button
        :class="{ active: modelValue === 'average' }"
        type="button"
        @click="active('average')"
      >
        Average
      </button>
    </li>
    <li>
      <button
        :class="{ active: modelValue === 'great' }"
        type="button"
        @click="active('great')"
      >
        Great
      </button>
    </li>
  </ul>
</template>
<script>
export default {
  props: ['modelValue'],
  emits: ['update:modelValue'],
  // data() {
  //   return {
  //     ActiveOptions: this.modelValue,
  //   };
  // },
  methods: {
    active(options) {
      this.$emit('update:modelValue', options);
    },
  },
};
</script>
<style scoped>
.active {
  border-color: #a00078;
}
.active button {
  color: #a00078;
}
ul {
  list-style: none;
  margin: 0.5rem 0;
  padding: 0;
  display: flex;
}
li {
  margin: 0 1rem;
  border: 1px solid #ccc;
  padding: 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
}
button {
  font: inherit;
  border: none;
  background-color: transparent;
  cursor: pointer;
}
</style>
