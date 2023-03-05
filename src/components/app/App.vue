<template>
  <div class="app font-monospace">
    <div class="content">
      <Appinfo v-bind:allQuotes="quotes.length" />
      <QuoteAddForm @createQuote="createQuote" />
      <div class="search-panel">
        <SearchPanel />
      </div>
      <QuoteList v-bind:quotes="quotes" @onRemove="onRemoveHandler" />
    </div>
  </div>
</template>

<script>
import Appinfo from "../app-info/Appinfo.vue";
import SearchPanel from "../search-panel/SearchPanel.vue";
import QuoteList from "../quote-list/QuoteList.vue";
import QuoteAddForm from "../quote-add-form/QuoteAddForm.vue";

export default {
  components: {
    Appinfo,
    SearchPanel,
    QuoteList,
    QuoteAddForm,
  },
  data() {
    return {
      quotes: [
        {
          id: 1,
          genre: "Жанр",
          text: "Lorem ipsum,впмвапвап sit amet consectetur adipisicing elit. Delectus quas ullam, ratione quis ea eius?",
          author: "Темур",
          createdTime: "15:23:44",
          updatedTime: "15:23:44",
        },
        {
          id: 2,
          genre: "Жанр1",
          text: "Lorolor sit amet consectetur adipisicing elit. Delectus quas ullam, ratione quis ea eius?",
          author: "Жавлон",
          createdTime: "12:23:45",
          updatedTime: "15:23:44",
        },
        {
          id: 3,
          genre: "Жанр2",
          text: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Delectus quas ullam, ratione quis ea eius?",
          author: "Туламов",
          createdTime: "11:22:33",
          updatedTime: "15:23:44",
        },
      ],
    };
  },
  methods: {
    createQuote(item) {
      this.quotes.push(item);
    },
    onRemoveHandler(id) {
      this.quotes = this.quotes.filter((c) => c.id !== id);
    },
  },
};
</script>

<style>
.app {
  height: 100vh;
  color: #000;
}
.content {
  width: 1000px;
  min-height: 700px;
  background-color: #fff;
  margin: 0 auto;
  padding: 5rem 0;
}
.search-panel {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
