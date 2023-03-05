<template>
  <div class="app font-monospace">
    <div class="content">
      <Appinfo />
      <QuoteAddForm />
      <div class="search-panel">
        <SearchPanel />
      </div>
      <QuoteList />
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
