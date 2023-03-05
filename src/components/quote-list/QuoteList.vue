<template lang="">
  <div class="quotes d-flex flex-wrap justify-content-center">
    <QuoteListitem v-for="quote in quotes" v-bind:quote='quote' />
  </div>
</template>

<script>
import QuoteListitem from "../quote-list-item/QuoteListitem.vue";
export default {
  components: {
    QuoteListitem,
  },
  data() {
    return {
      quotes: [
        {
          id: 1,
          genre: "Жанр",
          text: "Lorem ipsum,впмвапвап sit amet consectetur adipisicing elit. Delectus quas ullam, ratione quis ea eius?",
          author: "Темур",
        },
        {
          id: 2,
          genre: "Жанр1",
          text: "Lorolor sit amet consectetur adipisicing elit. Delectus quas ullam, ratione quis ea eius?",
          author: "Жавлон",
        },
        {
          id: 3,
          genre: "Жанр2",
          text: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Delectus quas ullam, ratione quis ea eius?",
          author: "Туламов",
        },
      ],
    };
  },
};
</script>

<style scoped>
.quotes {
  margin: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
