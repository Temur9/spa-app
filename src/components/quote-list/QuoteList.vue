<template lang="">
  <div class="quotes d-flex flex-wrap justify-content-center">
    <QuoteListitem
      v-for="quote in quotes"
      v-bind:quote="quote"
      :key="quote.id"
      @onRemove="$emit('onRemove', quote.id)"
      @onEdit="$emit('onEdit', index)"
    />
  </div>
</template>

<script>
import QuoteListitem from "../quote-list-item/QuoteListitem.vue";
export default {
  components: {
    QuoteListitem,
  },
  props: {
    quotes: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.quotes {
  margin: 2rem;
  padding: 1.5rem;
  background-color: #bcead5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
