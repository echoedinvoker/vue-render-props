<template>
  <li class="product">
    <p class="product-name">{{ product.productName }}</p>
    <p class="product-price">{{ product.price }}</p>
    <p class="product-description">{{ product.description }}</p>
  </li>
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({product: Object})
</script>
