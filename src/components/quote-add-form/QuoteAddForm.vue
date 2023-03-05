<template lang="">
  <div class="quote-add-form">
    <h3>Добавьте цитаты</h3>
    <form class="add-form d-flex flex-column">
      <input
        type="text"
        class="form-control new-quote-label"
        placeholder="Жанр"
      />
      <textarea class="form-control new-quote-label" placeholder='Цитата' cols="10" rows="10"></textarea>
      <input
        type="text"
        class="form-control new-quote-label"
        placeholder="Автор"
      />
      <button class="btn btn-outline-dark" type="submit">Добавить</button>
    </form>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.quote-add-form {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
textarea{
    resize: none;
}
</style>
