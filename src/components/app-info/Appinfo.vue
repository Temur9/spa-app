
<!-- Количество цитат -->
<template>
  <div class="app-info">
    <p class="fs-3 text-uppercase">Все цитаты: {{ allQuotes }}</p>
  </div>
</template>

<script>
export default{
  props:{
    allQuotes:{
      type:Number,
      required:true,
    }
  }
}
</script>

<style scoped>
.app-info {
  padding: 1.5rem;
  background-color: #BCEAD5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
