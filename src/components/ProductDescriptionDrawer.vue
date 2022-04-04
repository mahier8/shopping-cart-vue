<template>
  <div
    class="drawer-background"
    :class="{ show: active }"
    @click="$emit('close-product-drawer')"
  ></div>
  <div class="drawer" :show="{}">
    <div class="draw-close" @click="$emit('close-product-drawer')">X</div>
  </div>
</template>

<script>
export default {};
</script>

<style></style>
