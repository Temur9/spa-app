<template lang="">
  <div class="quote-add-form">
    <h3>Добавьте цитаты</h3>
    <form class="add-form d-flex flex-column">
      <input
        type="text"
        class="form-control new-quote-label"
        placeholder="Жанр"
        v-bind:value="genre"
        v-on:input="genre = $event.target.value"
      />
      <textarea
        class="form-control new-quote-label"
        placeholder="Цитата"
        cols="10"
        rows="10"
        v-bind:value="text"
        v-on:input="text = $event.target.value"
      ></textarea>
      <input
        type="text"
        class="form-control new-quote-label"
        placeholder="Автор"
        v-bind:value="author"
        v-on:input="author = $event.target.value"
      />
      <button class="btn btn-outline-dark" type="submit" @click="addQuote">
        Добавить
      </button>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      genre: "",
      text: "",
      author: "",
      createdTime: null,
    };
  },
  methods: {
    addQuote(e) {
      e.preventDefault();
      const newQuote = {
        id:Date.now(),
        genre: this.genre,
        text: this.text,
        author: this.author,
        createdTime:new Date().toLocaleTimeString(),
      };
      this.$emit("createQuote", newQuote);
      this.genre = "";
      this.text = "";
      this.author = "";
    },
  },
};
</script>
<style scoped>
.quote-add-form {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
textarea {
  resize: none;
}
</style>
