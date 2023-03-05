<template lang="">
  <input
    type="text"
    class="form-control search-input"
    placeholder="Поиск цитаты"
    v-bind:value="term"
    v-on:input="changeHandler"
  />
</template>

<script>
export default {
  props: {
    updateTermHandler: {
      type: Function,
      required: true,
    },
  },
  data() {
    return {
      term: "",
    };
  },
  methods: {
    changeHandler(e) {
      this.term = e.target.value;
      this.updateTermHandler(this.term);
    },
  },
};
</script>

<style scoped>
.search-input {
  margin-top: 2rem;
  padding: 1.5rem;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
