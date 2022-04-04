<template>
  <div class="home">
    <ProductDescriptionDrawer :item="item" :active="active.item_drawer" />

    <div class="product-cards-container">
      <!-- 1. for the loop 2. for the keys in the loop 3. for the props -->
      <ProductSummaryCard
        v-for="item in items"
        :key="item.id"
        :item="item"
        v-on:view-product="viewProduct($event)"
      />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import items from "../data/items";
import ProductSummaryCard from "../components/ProductSummaryCard.vue";
import ProductDescriptionDrawer from "../components/ProductDescriptionDrawer.vue";

export default {
  name: "Home",
  components: { ProductSummaryCard, ProductDescriptionDrawer },
  data() {
    return {
      items: items,
      item: null,
      active: {
        item_drawer: false,
      },
    };
  },
  methods: {
    viewProduct(item) {
      this.item = item;
      console.log(this.item);
    },
  },
};
</script>
<style lang="scss">
.product-cards-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
