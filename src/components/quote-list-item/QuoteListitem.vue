<template lang="">
  <div class="quote">
    <h5 class="quote-genre mb-3">{{ quote.genre }}</h5>
    <p class="quote-text">
      {{ quote.text }}
    </p>
    <h5 class="quote-author mb-3">{{ quote.author }}</h5>
    <div class="quote-times d-flex mb-4">
      <div class="created-time me-5">
        Создана: <br />
        {{ quote.createdTime }}
      </div>
      <div class="updated-time">
        Обновлена: <br />
        {{ quote.updatedTime }}
      </div>
    </div>
    <div class="quote-actions d-flex">
      <span class="fs-5 me-3 text-primary"
        ><i
          class="fa-solid fa-pen-to-square"
          @click="$emit('onEdit', quote.id)"
        ></i
      ></span>
      <span class="fs-5 text-danger" @click="$emit('onRemove', quote.id)"
        ><i class="fa-solid fa-trash"></i
      ></span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    quote: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.quote {
  width: 400px;
  background-color: #edf1d6;
  margin: 15px;
  padding: 10px;
  box-shadow: 4px 4px 8px 0px rgba(34, 60, 80, 0.2);
}
span {
  cursor: pointer;
}
</style>
