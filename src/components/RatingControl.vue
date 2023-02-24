<template>
  <ul>
    <li :class="{ active: modelValue === 'poor' }">
      <button type="button" @click="activated('poor')">Poor</button>
    </li>
    <li :class="{ active: modelValue === 'average' }">
      <button @click="activated('average')" type="button">Average</button>
    </li>
    <li :class="{ active: modelValue === 'great' }">
      <button type="button" @click="activated('great')">Great</button>
    </li>
  </ul>
</template>
<script>
export default {
  props: ["modelValue"],
  emits: ["update:modelValue"],
  methods: {
    activated(option) {
      this.$emit("update:modelValue", option);
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
  padding: 1rem;
  margin: 0 1rem;
  border: 1px solid #ccc;
  display: flex;
  justify-content: center;
  align-content: center;
}
button {
  font: inherit;
  background-color: transparent;
  cursor: pointer;
  border: none;
}
</style>