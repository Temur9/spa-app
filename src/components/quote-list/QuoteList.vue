<template lang="">
  <div class="quotes d-flex flex-wrap justify-content-center">
    <QuoteListitem/>
  </div>
</template>

<script>
import QuoteListitem from '../quote-list-item/QuoteListitem.vue';
export default {
  components:{
    QuoteListitem,
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
