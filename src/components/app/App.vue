<template>
  <div class="app font-monospace">
    <div class="content">
      <Appinfo v-bind:allQuotes="quotes.length" />
      <QuoteAddForm @createQuote="createQuote" />
      <div class="search-panel">
        <SearchPanel v-bind:updateTermHandler="updateTermHandler" />
      </div>
      <QuoteList
        v-bind:quotes="onSearchHandler(quotes, term)"
        @onRemove="onRemoveHandler"
        @onEdit="onEditHandler"
      />
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
      term: "",
      quote: "",
      editedQuote: null,
    };
  },
  methods: {
    // Функция для добавления новуя цитату
    createQuote(item) {
      this.quotes.push(item);
    },

    // Функция для удаления цитаты
    onRemoveHandler(id) {
      
      if (confirm("Хотите удалить?")) {
        this.quotes = this.quotes.filter((c) => c.id !== id);
      }
      return quotes;
    },

    // Функция для поиска цитаты
    onSearchHandler(arr, term) {
      if (term.length === 0) {
        return arr;
      }
      return arr.filter((c) => c.author.toLowerCase().indexOf(term) > -1);
    },
    updateTermHandler(term) {
      this.term = term;
    },

    // Функция для изменения
    onEditHandler(index) {
      this.quote = this.quotes[index].genre;
      this.editedQuote = index;
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
  max-width: 1000px;
  min-height: 700px;
  background-color: #fff;
  margin: 0 auto;
  padding: 5rem 0;
}
.search-panel {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #def5e5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
