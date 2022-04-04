<template>
  <div class="card">
    <h3>{{ item.name }}</h3>

    <h5 class="price">Price: ${{ item.price.toFixed(2) }}</h5>
    <p class="description">Description: {{ description }}...</p>
    <p class="text-muted">{{ item.category }}</p>
    <button @click="$emit('view-product', item)" class="view-product-button">
      View Products
    </button>
  </div>
</template>

<script>
export default {
  props: ["item"],
  computed: {
    description() {
      return this.item.description.substring(0, 150);
    },
  },
};
</script>

<style lang="scss">
.card {
  width: 80%;
  margin: 10%;
  padding: 10px;
  border-radius: 5px;
  border-color: white;
  box-shadow: 0 0 5px gray;

  h5.price {
    color: gray;
  }

  p.description {
    font-size: 0.85rem;
  }

  p .text-muted {
    color: gray;
  }

  button.view-product-button {
    padding: 10px;
    background-color: rgb(79, 160, 187);
    border: none;
    color: white;
    font-weight: bold;
    font-size: 1.15rem;
    border-radius: 5px;
    cursor: pointer;
  }
}

@media (min-width: 500px) {
  .card {
    width: 350px;
    margin: 10px;
  }
}
</style>
